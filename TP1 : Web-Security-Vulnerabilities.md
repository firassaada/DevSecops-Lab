# 6  OS command injection, simple case :

We did sucessfully inject the os command :

![image](https://github.com/firassaada/DevSecops-Lab/assets/94303698/465e6a75-69c7-4ed3-a14c-d56cfaeb3428)

![image](https://github.com/firassaada/DevSecops-Lab/assets/94303698/4e2632e0-8627-4407-be4d-e9148a537b34)

# 7 File path traversal, simple case :

we have changed the path of the image to ../../../etc/passwd and that way we can access critical information on the host machine server :

![image](https://github.com/firassaada/DevSecops-Lab/assets/94303698/ad12a04f-2dfe-4178-96ea-55933f9803c6)

![image](https://github.com/firassaada/DevSecops-Lab/assets/94303698/b7af17a2-7c01-4e4d-ad42-aefe51e30523)

![image](https://github.com/firassaada/DevSecops-Lab/assets/94303698/8ec401be-0ace-4664-9b6f-2a84b5acbe4d)

# 8  Unprotected admin functionality :

We have correctly guessed the path to access as an administrator which was not protected and we were able to delete all users(we can use force brute) :

![image](https://github.com/firassaada/DevSecops-Lab/assets/94303698/d30c1f48-9751-406d-9066-d1720c45d177)

![image](https://github.com/firassaada/DevSecops-Lab/assets/94303698/6a133f12-2650-4e29-ba22-e7b0a1f82209)

# 9 Password reset broken logic :

We can send the request without the password token so we used that vulnerability to change the password of the username carlos :

![image](https://github.com/firassaada/DevSecops-Lab/assets/94303698/64ab10ce-7b9f-4456-906b-6910151e1703)

![image](https://github.com/firassaada/DevSecops-Lab/assets/94303698/f49dbcf1-bbd4-46c5-b66d-20b6a348ac05)

![image](https://github.com/firassaada/DevSecops-Lab/assets/94303698/f3d32a17-7cdd-4253-b3fd-525acbc96261)

# 10  Information disclosure in error messages : 

we can see that after changing the id from a number to a string we managed to get a
server error 500 and that way we are able to get the version number :
![image](https://github.com/firassaada/DevSecops-Lab/assets/94303698/9155b6a0-afed-40ae-b0b6-822355be7eb1)

![image](https://github.com/firassaada/DevSecops-Lab/assets/94303698/75a55d49-d425-41bc-9f56-be96753d70f1)
