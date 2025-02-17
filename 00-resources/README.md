# <img src="../assets/img/k8s.png" width="30px"> **Kubernetes** - ***Section 0:*** `Resources` 🗃️

<!-- 

replacing md links with html links

regex: \[\*\*([A-z0-9- *]{1,})\*\*\]\((https://[A-z0-9-./]{1,})\)
replace: <a href="$2" target="_blank">***$1***</a> 

-->


## ***Table*** *of* ***`Contents`*** 📜

* 🏠 [**home**](../README.md)
* 🗃️ **resources**
  * 📁 **pdfs**
    * 📖 <a href="https://aguerrero232.github.io/kubernetes-zero-to-pro/00-resources/pdfs/kubernetes-up-and-running.pdf" target="_blank">***kubernetes up and running***</a>
  * 🔗 **links**
    * 🎓 <a href="https://www.cncf.io/certification/ckad/" target="_blank">***certified kubernetes application developer test***</a>
    * 💪 <a href="https://github.com/dgkanatsios/CKAD-exercises" target="_blank">***exercises for CKAD***</a>
    * 🙇🏻‍♀️ <a href="https://github.com/lucassha/CKAD-resources" target="_blank">***study materials for CKAD***</a>
    * 🤔 <a href="https://kubernetes.io/docs/concepts/" target="_blank">***kubernetes concepts***</a>
    * 📓 <a href="https://www.cncf.io/certification/candidate-handbook" target="_blank">***candidate handbook***</a>
    * 💡 <a href="https://docs.linuxfoundation.org/tc-docs/certification/tips-cka-and-ckad" target="_blank">***exam tips***</a>

<br />

## **Description** 👀

Resources for the `Kubernetes` ***Zero to Pro Guide***. Has images, pdfs, and links to other resources.

<br />

## **Helpful** `Content` 📌

This is a collection of helpful content for the `Kubernetes` ***Zero to Pro Guide***. It is not a part of `Kubernetes`, but it is helpful for learning `Kubernetes`.

## ***YAML***  <img src="../assets/img/yaml.png" width="26px">

`YAML` is a ***human-readable data serialization language***. It is commonly used for *configuration files* and in applications where data is being stored or transmitted. `YAML` is stored in **key value pairs** and can be used to serialize data structures such as *maps, sequences, and scalars*.

### `YAML` **Syntax**

* `YAML` is case sensitive
* Comments are created using the # symbol

### **Examples** 🧩

* key value pairs

  ```yaml
  Fruit: Apple
  Vegetable: Carrot
  Liquid: Water
  Meat: Chicken
  ```

* arrays / lists

  ```yaml
  Fruits:
    - Orange
    - Apple
    - Banana

  Vegetables:
    - Carrot 
    - Cauliflower
    - Tomato
  ```

* dictionary / map

  ```yaml
  Banana:
      Calories: 105
      Fat: 0.4g
      Carbs: 27g

  Grapes:
      Calories: 62
      Fat: 0.3g
      Carbs: 16g
  ```

* key value / dictionary / lists

  ```yaml
  Fruits:
    - Banana:
        Calories: 105
        Fat: 0.4g
        Carbs: 27g

    - Grapes:
        Calories: 62
        Fat: 0.3g
        Carbs: 16g
  ```

***Notice the alignment, this is important in yaml.***

* You can *either* set a value or a list/dictionary/map but *not both*

* `Dictionaries` are an *unordered collection* while `lists` are *ordered*

<br>

## ***Docker*** 🐳

`Docker` is a ***containerization platform*** that allows you to *package* and *run* an application in a loosely isolated environment called a *container*. `Docker` is a ***client-server*** application with the `Docker` daemon running on the host and the `Docker` client from the command line or from a program.

### How To Create Your Own Image?

* `Dockerfile` - a text document that contains all the commands a user could call on the command line to assemble an image

  Very Basic Outline:
  1. pick an os. i.e. `ubuntu`
  2. update `apt` repo
  3. install dependencies using `apt`
  4. install dependencies using `pip`
  5. copy source code into container directory `/app`, `/src`, `/opt` etc.
  6. run the web server, or application

  <br />

    ```Dockerfile
    # sample Dockerfile for steps outlined above
    FROM Ubuntu
    RUN apt-get update
    RUN apt-get install python
    RUN pip install flask
    RUN pip install flask-mysql
    COPY . /opt/source-code
    ENTRYPOINT FLASK_APP=/opt/source-code/app.py flask run
    ```

  * all `Dockerfiles` must start with `FROM`

* build the image using the `docker build` command.

  ```shell
  docker build Dockerfile -t <image-name> 
  ```

  * `-t` - tag the image

* **view** image `operating system`

  ```shell
  docker image inspect <image-name>
  ```

  or

  ``` shell
  docker run <image-name>  cat /etc/os-release
  ```

<br>


## ***Helm*** <img src="../assets/img/helm.svg" width="26px" />

`Kubernetes` does not care about you application as a whole, it cares about the *individual* components. `Helm` is a ***package manager*** for `Kubernetes` that allows you to *package up your application as a whole* and *deploy* it to `Kubernetes`.

<br>

### **Basic** `Commands` 📝

* install application using `helm install`

  ```shell
  helm install <application-name> <chart-name>
  ```

* uninstall application using `helm uninstall`

  ```shell
  helm uninstall <application-name>
  ```

* view application using `helm list`

  ```shell
  helm list
  ```

* view application details using `helm status`

  ```shell
  helm status <application-name>
  ```

* upgrade application using `helm upgrade`

  ```shell
  helm upgrade <application-name> <chart-name>
  ```

* rollback application using `helm rollback`

  ```shell
  helm rollback <application-name> <revision-number>
  ```


<br>

## ***Nano*** 📝

`Nano` is a *text editor* that is installed by default on most Linux distributions. It is a simple text editor that is easy to use and has a lot of features. During the `CKAD` exam, you will be **asked to edit a file using Nano or Vim**.

* 🗎 <a href="https://www.nano-editor.org/" target="_blank">***nano documentation***</a>

### ***Initial `Setup`*** 🛠️

* `nano` config file, ***~/.nanorc***

    ```bash
    set tabsize 2
    set tabstospaces
    ```

  * `tabsize` - sets the number of spaces that a tab will be replaced with

  * `tabstospaces` - replaces tabs with spaces

  * if ***~/.nanorc*** *does not exist*, **create** it

      ```shell
      touch ~/.nanorc
      ```

### ***Keyboard `Shortcuts`*** ⌨️

<!-- regex for matching the commands for formatting -->
<!-- Ctrl\+[A-z0-9]{1,} -->
<!-- Alt\+[A-z0-9]{1,} -->

* **editing**
  * `Ctrl+K`    Cut current line into cutbuffer
  * `Alt+6` Copy current line into cutbuffer
  * `Ctrl+U` Paste contents of cutbuffer
  * `Alt+T` Cut until end of buffer
  * `Ctrl+]` Complete current word
  * `Alt+3` Comment/uncomment line/region
  * `Alt+U` Undo last action
  * `Alt+E` Redo last undone action

* **search** *and* **replace**
  * `Ctrl+Q`    Start backward search
  * `Ctrl+W` Start forward search
  * `Alt+Q` Find next occurrence backward
  * `Alt+W` Find next occurrence forward
  * `Alt+R` Start a replacing session

* **deletion**
  * `Ctrl+H` Delete character before cursor
  * `Ctrl+D` Delete character under cursor
  * `Alt+Bsp` Delete word to the left
  * `Ctrl+Del`    Delete word to the right
  * `Alt+Del` Delete current line

* **moving around**
  * `Ctrl+B`    One character backward
  * `Ctrl+F` One character forward
  * `Ctrl+←`One word backward
  * `Ctrl+→`One word forward
  * `Ctrl+A` To start of line
  * `Ctrl+E` To end of line
  * `Ctrl+P` One line up
  * `Ctrl+N` One line down
  * `Ctrl+↑`To previous block
  * `Ctrl+↓`To next block
  * `Ctrl+Y` One page up
  * `Ctrl+V` One page down
  * `Alt+\` To top of buffer
  * `Alt+/`To end of buffer
