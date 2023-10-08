## Build and Test the Image
1.Build the image:

`docker build . -t web`

2.Check that we have the web image:

`docker image ls` 

3.Launch Docker based on the web image:

`docker run -dt -p 8080:80 --name web01 web` 

4.Once it is finished running, check that the website has been launched:

`curl localhost:8080` 
We will get the HTML for the website.

5.Copy the public IP address provided on the lab page, and paste it into a new browser tab. We'll know it worked correctly when the Container Hub website appears.
http://sandboxdevops.southeastasia.cloudapp.azure.com:8080/
