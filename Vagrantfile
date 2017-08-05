# -*- mode: ruby -*-

# Partie 1 : On cree une configuration vagrant
Vagrant.configure(2) do |config|

  # Partie 2 : Definir le systeme que l'on utilise (/!\ Il faut que ce soit exactement la meme valeur pour la Partie 3)
  config.vm.box = "debian/jessie64"

  # Partie 3 : Definir l'url de la box (voir http://)
  config.vm.box_url = "debian/jessie64"

  # Partie 4 (facultatif) : On defini le nom du serveur
  config.vm.hostname = "NomMachine"

  # Partie 5 (facultatif) : On configure la carte reseau
  
  # Pour du reseau prive
  # config.vm.network "private_network", ip: "192.168.1.24"				# /!\ Il faut mettre une ip differente de l'hote

  # OU

  # Pour du reseau publique en mode acces par pont
  config.vm.network "public_network", bridge: "NomDeLaCarteReseau"			# /!\ Fonctionne avec le DHCP du reseau de l'hote

  # Partie 6 : Choix et configuration de l'application de virtualisation (autrement dit : choix de l'hyperviseur et configuration de la "Virtual Machine"
  config.vm.provider "virtualbox" do |vb|		# Precise le provider (virtualbox, vmware, Microsoft Azure, etc.) cible pour la creation d'une vm
  
    # vb.gui = true     				# Ouvre la session virtualbox quand la machine virtualle sera prete
    # vb.memory = "2048"				# Precise la quantite de ram pour la vm en octet
    vb.name = "NomMachine" 				# Defini le nom de la machine virtuelle
    vb.cpus = "3"					# Precise le nombre de processeur pour la machine virtuelle
  end

  # Partie 7 (facultatif) : On defini le "provision" (ansible, puppet, chef, etc.) pour deployer une configuration systeme ou applicative

  # Type de "provision" : ansible
  config.vm.provision "ansible" do |ansible|
	ansible.playbook = "recettes.yml"	# On precise l'emplacement de la fiche de recette ansible
  end
end
