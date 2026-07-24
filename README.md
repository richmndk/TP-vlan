Home TP : j'ai configuré un petit TP Vlan sur packet tracer.

objectif: comprendre comment séparer les flux réseau d'une entreprise. ici j'ai deux Vlans Vlan 1O = comptabilité et Vlan 20 = direction 
A)
-les hôtes de vlan 10 pourront communiquer ensemble 
-les hôtes de vlan 20 pourront communiquer ensemnle
- les hôtes issus de Vlan 10 et Vlan 20 ne pourront pas communiquer ensemble.


outils de simulations packet tracer:
 1 commutateur 
 4 ordinateurs

vlan 10 : comptabilité
-ordinateur 0 - 1 , port: fastethernet 0/1-2 
- ip :192.168.10.10 - 192.168.10.11
- masque de sous-reseau:255.255.255.0


vlan 20: Direction
-ordinateur 2-3 , port : fastethernet 0/3-4
-ip: 192.168.20.10 - 192.168.20.11
-masque de sous-reseau : 255.255.255.0

B) configurer le commutateur
  1) passer en mode de privilège
   enable
   configure terminal
2) créer les vlans
    vlan 10 qui est comptabilité
     name comptabilité
      exit

   vlan 20 qui est Direction
     name Direction
     exit

   Affecter les ports de vlan 10 , pareil pour vlan 20

      interface range fastethernet 0/1 - 2
   switchport mode access
   switchport access vlan 10
   exit

 et après il faut enregister:
 end 
 copy run start

 

   




C) commande de vérification
show vlan brief
