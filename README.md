# docker
Docker, tips, tools, studdy material


# Docker File Structure

# escape=`      -> (OPTIONAL) Parser Directives  
                - Scope only the next instruction
                - Example change escape char for windows power shell
               
ENV name=value  -> (OPTIONAL) Environmental Variables 
    name value  - set a value that can be used at build time and later in the container

ARG name=value  -> (OPTIONAL) is the only instruction that may precede FROM in the Dockerfile
                - set a key value var to be use in the next instruction
                - Scope of the call ARG per instruction, Use ARG arg_name to re-use it

FROM            -> (MANDATORY - HAVE TO BE THE FIRST INSTRUCTION)
                - Set the base image to use as first layer
                
RUN ["executable", "param1", "param2"]
                -> (OPTIONAL) Execute a program in shell using the actual layer and the result is the next layer.
                - The program do not have to be inside the layer
                - Is possible to choose the runing shell

CMD ["executable","param1","param2"] 
CMD command param1 param2
                -> (OPTIONAL) Provide a command line arguments to run the image

LABEL <key>=<value> <key>=<value> <key>=<value> ...
                -> (OPTIONAL) Add metatags to the image

EXPOSE port_num -> (OPTIONAL) Set the default port for the image

ADD <src> <dest> -> (OPTIONAL) Copy files to the image
    ["<src>",... "<dest>"] (this form is required for paths containing whitespace)
                -> Multiples src allowed, possible to use wildcards    

    -----------------------------
    The Build action is doing by the docker Daemon
    .dockerignore files allow you to eclude/include files using paths patterns wildcards wildcards at build time
    the action of include or exclude is doing by the deamon, so all files are send it with de docker files
    
    

