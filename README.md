# docker-exe1
Dans une commande docker run
* vous devez etre en interactif et avec un tty pour le display
* le container doit etre nommé **myalpes** 
* dans cette commande creer un volume /MountPoint
* image doit etre alpine
* passer la commande /bin/ash 

      docker run -it --name myalpes -v /MountPoint alpine /bin/ash
    
Ensuite a l'interieur du container  
* creer un fichier test.py
* et inserez le texte "WARNING: ret pointer is null"

      cd /MountPoint
      touch test.py
      echo "WARNING: ret pointer is null" > test.py      
      
A partir de ce container créer une image nommée  myalpine:v12.

      docker commit myalpes myalpine:v12

* Supprimer les metadata de cette image avec docker export et docker import 

    

* Verifier avec docker history 

      docker history myalpine:v13

* mettez cette image dans docker hub sous votre compte docker hub
      
      docker login -u <docker_hub_account> -p <password>
      docker pull alpine
      docker image tag alpine <docker_hub_account>/myfirstimage
      docker push <docker_hub_account>/myfirstimage
