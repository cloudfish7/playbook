UserData on EC2 add the this code.

    #!/bin/sh
    yum update -y
    yum install epel-release -y
    yum install gcc python-devel python-crypto python-pip git -y
    easy_install pip
    pip install ansible
    git clone https://github.com/shogomuranushi/playbook.git
    cat <<EOF > playbook/roles/common/vars/main.yml
    user:
     - { ssh_user: joy }
     - { ssh_user: tom }
    EOF
    ansible-playbook playbook/main.yml
    # Remove the comment, if necessary.
    # ansible-playbook playbook/nrpe.yml
    # ansible-playbook playbook/apache.yml
    # ansible-playbook playbook/php.yml --extra-vars "pkg=php53"
