[![Build Status](https://travis-ci.org/ansible/ansible-container.svg)](https://travis-ci.org/ansible/ansible-container)
[![Code Coverage](https://codecov.io/gh/ansible/ansible-container/coverage.svg)](https://codecov.io/gh/ansible/ansible-container)

# Ansible Container

Ansible Container is a tool for building Docker images and orchestrating containers using Ansible playbooks.

## How it works

Use Ansible Container to manage the container lifecycle from development, through testing, to production:

* `ansible-container init`

  Creates a directory *ansible* with files to get you started. Read the comments, and edit to suit your needs.

* `ansible-container install`

  Downloads Ansible-Container-ready roles from [Ansible Galaxy](https://galaxy.ansible.com), and installs them in your project.

* `ansible-container build`

  Creates images from your Ansible playbooks.

* `ansible-container run`

  Launches the containers specified in the orchestration document, *container.yml*, for testing the built images. The 
  format of *container.yml* is nearly identical to Docker Compose.

* `ansible-container push`

  Pushes the project's container images to a registry of your choice.

* `ansible-container shipit`

  Generates a playbook and role capable of deploying the project on a supported cloud provider.

## Installing

Install using *pip*, the Python package manager:

    $ sudo pip install ansible-container
    
Or, to install without root privileges, use [virtualenv](https://virtualenv.pypa.io/en/stable/) to first create a 
Python sandbox:
    
    $ virtualenv ansible-container
    $ source ansible-container/bin/activate
    $ pip install ansible-container

For more details, prerequisite, and instructions on installing the latest development release, please view our 
[Installation Guide](https://docs.ansible.com/ansible-container/installation.html).


## Getting started

For examples and a tour of Ansible Container [visit our docs site](https://docs.ansible.com/ansible-container/).

If you just can't wait, the following provides a quick install and run of our [demo project](https://galaxy.ansible.com/chouseknecht/django-gulp-nginx). But before continuing, you *must* [install from source](http://docs.ansible.com/ansible-container/installation.html#running-from-source), so that you have the latest code.

Setup the demo locally by running the following commands to create an empty directory named *demo*, and initialize it with a copy of the project:

```
# Create a directory named 'demo'
$ mkdir demo

# Set the working directory to 'demo'
$ cd demo

# Initialize the project
$ ansible-container init chouseknecht.django-gulp-nginx
```

Now that you have a copy of the project, you can build the container images by running the following command from within the *demo* directory:

```
# Start the image build 
$ ansible-container build
```

The build will run for serveral minutes, and playbook task names will be displayed as the build progresses. Once the build completes, you'll have a local copy of the images, and you'll be ready to launch the application by running the following:

```
# Launch the application
$ ansible-container run
```

With the containers running, the demo web server is now accessible from a web browser at [http://localhost:8080](http://localhost:8080). For more details about the application, please visit the [project repo](https://github.com/chouseknecht/django-gulp-nginx).

## Get Involved

* Visit [Community Information and Contributing](https://docs.ansible.com/ansible-container/community/index.html) 
  for all kinds of ways to contribute to and interact with the project. We welcome your feedback and ideas!
* Review [CONTRIBUTORS.md](./CONTRIBUTORS.md), if you're considering submitting code.
* [Join the  mailing list](https://groups.google.com/forum/#!forum/ansible-container)
* [Open an issue](https://github.com/ansible/ansible-container/issues)
* Join the #ansible-container channel on irc.freenode.net.  

## Branch Information

 * The *develop* branch is the release actively under development.
 * The *master* branch corresponds to the latest stable release available at [PyPi](https://pypi.org/project/ansible-container/).
 * Submit pull requests for bug fixes and new features to *develop*.
 * View [the roadmap](./ROADMAP.rst) for a list of features currently under development.
 * Contributors welcome! Get started by reviewing [CONTRIBUTORS.md](./CONTRIBUTORS.md).

## Authors

View [AUTHORS](./AUTHORS) for a list contributors to Ansible Container. Thanks everyone!

Ansible Container is an [Ansible by Red Hat](https://ansible.com) sponsored project.
