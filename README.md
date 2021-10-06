# CI-DevOps


### Task 0: Install a ubuntu 18.04 server 64-bit
either in a physical machine or a virtual machine
http://releases.ubuntu.com/18.04/
https://www.virtualbox.org/

### Task 1: N/A

### Task 2: N/A

### Task 3: install a single node Kubernetes cluster minikube using kubeadm
https://kubernetes.io/docs/setup/independent/create-cluster-kubeadm/


### Task 4: install gitlab-ce version in vm
https://about.gitlab.com/install/#ubuntu?version=ce
Expect output: Gitlab is up and running at http://127.0.0.1 (no tls or FQDN required)
Access it from host machine http://127.0.0.1:8080

### Task 5: create a demo group/project in gitlab
named demo/go-web-hello-world (demo is group name, go-web-hello-world is project name).

Use golang to build a hello world web app (listen to 8081 port) and check-in the code to master.
https://golang.org/<br>
https://gowebexamples.com/hello-world/

Expect source code at http://127.0.0.1:8080/demo/go-web-hello-world

### Task 6: build the app and expose ($ go run) the service to 8081 port

Expect output: 
```
curl http://127.0.0.1:8081
Go Web Hello World!
```

### Task 7: document the procedure in a MarkDown file
create a README.md file in the gitlab repo and add the technical procedure above (0-6) in this file

-----------------------------------

### Task 8: install Jenkins with yaml file in the Kubernetes cluster installed in task3
https://www.jenkins.io/doc/book/installing/kubernetes/

expose the Jenkins pod as service with nodePort type port 8082

Expect output: Jenkins is up and running at http://<minikube-ip>:<port> (no tls or FQDN required)

Create a folder jenkins in the gitlab project http://127.0.0.1:8080/demo/go-web-hello-world
•	checkin all the yaml file which used for Jenkins deployment jenkins folder.
•	record the technical procedure in README.md file created in task7

## Task 9: create a demo CI pipeline, be triggered by any commit of the repo http://127.0.0.1:8080/demo/go-web-hello-world master branch. 
Jenkins & gitlab integration
Use Jenkinsfile to define the pipeline.
This pipeline shall be triggered by every commit to gitlab project http://<gitlab-url>/demo/go-web-hello-world  master branch
Task6(build go project) shall be part of the pipeline. 
