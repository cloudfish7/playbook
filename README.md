UserData on EC2 add the this code.

    yum install epel-release -y
    yum install gcc python-devel python-crypto python-pip git -y
    easy_install pip
    pip install ansible
    git clone https://github.com/shogomuranushi/playbook.git
    ansible-playbook playbook/main.yml
    # Remove the comment, if necessary.
    # ansible-playbook playbook/nrpe.yml
    # ansible-playbook playbook/apache.yml --extra-vars "pkg=httpd"
    # ansible-playbook playbook/apache.yml --extra-vars "pkg=httpd24"
