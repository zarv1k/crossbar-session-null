Repo for reproducing 'session ID=null' issue in crossbar.io while disconnect from router with dynamic async authenticator during session establishment
====

This example is created for help with reproducing issue (I called it 'session ID=null'). 
Example is mostly based on [dynamic ticket authenticator](https://github.com/crossbario/crossbar-examples/tree/master/authentication/ticket/dynamic) example.

How to reproduce
---

1. Run docker container:

    ```bash
    $ docker run -it --rm -p 8080:8080 --name crossbar_session_null_issue \
        -v $(pwd)/.crossbar:/node/.crossbar \
        -v $(pwd)/web:/node/web \
        -v $(pwd)/authenticator.py:/node/authenticator.py \
        crossbario/crossbar:latest
    
    ```
    You can also use docker-compose:
    ```bash
        $ docker-compose up -d        
    ```
2. Open `http://localhost:8080` in your browser, which supports Promises (e.g. Chrome 65) and follow the steps on webpage.