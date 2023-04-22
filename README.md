# AutoGPT-install-macm1
To achieve the goal of installing AutoGPT on an Apple M1 device, the first phase involves obtaining the necessary components. While there are already published browser-based solutions available, I personally did not feel comfortable adding my OpenAI API key to a third-party website. As a result, I aim to create my own local environment on my computer.

To accomplish this, I require my own Google Custom Search Engine and API key, which can be obtained by creating a Google Account and adding a new Search Engine that searches the internet as a whole. I have described the entire process in detail in my repository.

https://programmablesearchengine.google.com/controlpanel/all

And you can get cx code from your custom search engine url after this 
![image](https://user-images.githubusercontent.com/6028261/233764239-e7d45f47-7f40-4186-9e5b-7e0cd2b37a05.png)

You can also create the API key in this same service

Save both of these for the next phase.

Offcourse you need also OpenAI API keys and it cannot be the free one. So go the OpenAI site and make purchase options that are best for you. You can limit the amount of usage per month for example.

Cloning the AutoGPT command line

```git clone git@github.com:Significant-Gravitas/Auto-GPT.git```

finding out from the documentation tha Main Branch could be broken. That means that i need to checkout the exact version with Git I can do it with
 ```git checkout versionumber ```
 
 But Then i looked they repo and there is the stable Branch. So I went the folder and put
 
 ```git switch stable```
 
 I had the VSCode installed with command line tools so I commanded in Auto-GPT folder:
 
 ```code .```
It opened the VSCode Project.

I Had the python3 installed
```
Auto-GPT git:(stable) python3 --version
Python 3.11.3
```
And I had docker installed 
```
➜  Auto-GPT git:(stable) docker --version
Docker version 20.10.17, build 100c701
 
```
I took copy of the .env file

```
cp .env.template .env
```
I decided to use Redis as a database so I installed the redis container
```
docker run -d --name redis-stack-server -p 6379:6379 redis/redis-stack-server:latest
```

![image](https://user-images.githubusercontent.com/6028261/233770467-f10fb22a-7d21-47aa-b9d0-d8d17a42dcb1.png)


It seems to running ok in my computer.

There was promblem with command

```
./run.sh start
```
It was because it tries to run command python which didn't work in my mac. I tried it with alias but there was still problems

```
Auto-GPT git:(stable) ✗ ./run.sh start
./run.sh: line 3: python: command not found
./run.sh: line 9: python: command not found
Press any key to continue...
```
Next I just run the AutoGPT with python. Installing first requirements
```
 pip install -r requirements.txt

```
And then running the actual AutoGPT

```
python3 -m autogpt
```
Now I've got it starting









