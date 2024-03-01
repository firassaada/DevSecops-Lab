# 1 SQL Injection:

![sqli1](https://github.com/firassaada/DevSecops-Lab/assets/92325496/4c51337c-6568-41a8-8aa9-f3dac26ac587)


When accessing the products list page , it only shows 3 products for the accessories category : 

![sql2](https://github.com/firassaada/DevSecops-Lab/assets/92325496/10f38e27-bf8e-44f5-bd32-fc4b56a36b94)

using burp suite we can intercept the request to inject some sql to the query param seach :

![sql3](https://github.com/firassaada/DevSecops-Lab/assets/92325496/0baae785-7fde-46cd-a6a8-2f3c887b0a08)

this way we will be getting another list of products that contains some products that are not shown in the accessories category and even not shown when selecting the "All" filter :

![sql4](https://github.com/firassaada/DevSecops-Lab/assets/92325496/48a0e959-2b7c-4ae2-ac11-dc5a52f72827)

# 2 Cross Site Scripting :

a-First Lab : Reflected XSS into HTML context with nothing encoded:

in this lab we will be injecting some javascript in the search field : 

![xss1](https://github.com/firassaada/DevSecops-Lab/assets/92325496/5c108eb6-495a-407f-889a-72d186dda0ce)

this way we will be getting this as a result when clicking on "Search" button :

![xss2](https://github.com/firassaada/DevSecops-Lab/assets/92325496/41c53e32-0909-45ce-a4ff-1984014650f5)

b-Second Lab : Stored XSS into HTML context with nothing encoded:

after checking the vulnerability of the field name,email , website and comment , we discovered that the comment field doesn't have any time of control on the input so this is gonna be our target to peform the attack :

![xss3](https://github.com/firassaada/DevSecops-Lab/assets/92325496/ace7f98c-90ad-4e38-ab24-dac0ab2b8c78)

we submit the comment and go back to the blog and here is the result of the attack :

![xss4](https://github.com/firassaada/DevSecops-Lab/assets/92325496/378505da-de36-45f6-b882-8fa4444741f0)

![xss5](https://github.com/firassaada/DevSecops-Lab/assets/92325496/7695f7db-1288-4444-b351-31ec4c9da343)

c-Third Lab : DOM XSS in document.write sink using source location.search :

We wrote "investigating" in the search field and we submitted : 

![xss6](https://github.com/firassaada/DevSecops-Lab/assets/92325496/0e50ec41-185f-439e-b4f2-6ccd2d668075)

at that point we discovered that the result of the submission is creating an img element containing the search input field value : 

![xss7](https://github.com/firassaada/DevSecops-Lab/assets/92325496/d3964339-605c-43c4-8561-7a3401b6d89a)

so we tried to perform the attack using this search field :

![xss8](https://github.com/firassaada/DevSecops-Lab/assets/92325496/a2e92473-80ff-437e-9d2c-e14054b91188)

and here is the result :

![xss9](https://github.com/firassaada/DevSecops-Lab/assets/92325496/dded7528-7875-41d0-b48a-9d958751209e)

# 5 XXE Injection : 

When submitting the request using the check store button , and inspecting the request from burp suite , we discovered that the we can inject the some xml in the request body since they are using xml format on the body of the request : 

![lab5-1](https://github.com/firassaada/DevSecops-Lab/assets/92325496/43ae139a-1bef-436b-bf86-2feed6a6568c)

that way we had the ability to get the content of the file /etc/passwd when getting the response of the request : 

![lab5-2](https://github.com/firassaada/DevSecops-Lab/assets/92325496/170435d0-0630-421e-998f-b5ed5a685dca)


# 6  OS command injection, simple case :

![image](https://github.com/firassaada/DevSecops-Lab/assets/94303698/465e6a75-69c7-4ed3-a14c-d56cfaeb3428)

![image](https://github.com/firassaada/DevSecops-Lab/assets/94303698/4e2632e0-8627-4407-be4d-e9148a537b34)
