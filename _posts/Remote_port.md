https://docs.anaconda.com/anaconda/user-guide/tasks/remote-jupyter-notebook/

# Replace <PORT> with your selected port number
jupyter notebook --no-browser --port=<PORT>

# Replace <PORT> with the port number you selected in the above step
# Replace <REMOTE_USER> with the remote server username
# Replace <REMOTE_HOST> with your remote server address
ssh -L 8080:localhost:<PORT> <REMOTE_USER>@<REMOTE_HOST>


Open a browser from your local machine and navigate to http://localhost:8080/, the Jupyter Notebook web interface. Replace 8080 with your port number used in step 1.
