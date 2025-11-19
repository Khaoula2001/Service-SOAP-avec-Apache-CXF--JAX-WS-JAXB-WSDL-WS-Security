# Service SOAP avec Apache CXF (JAX-WS, JAXB, WS-Security)

Implémentation d’un petit service SOAP avec Apache CXF : opérations `SayHello` et `FindPerson`, modèle JAXB, exposition WSDL et sécurisation WS-Security (UsernameToken).

![Structure du projet](./screens/2025-11-15_15h09_48.png)

## Lancer le service
- Construire le projet : `mvn clean package`
- Démarrer le serveur simple : exécuter la classe `Server`.
- Démarrer le serveur sécurisé (UsernameToken) : exécuter la classe `SecureServer`.

Exemple de log (secure) :
![Démarrage serveur sécurisé](./screens/2025-11-16_17h00_29.png)

## WSDL
- Service non sécurisé : http://localhost:8080/services/hello?wsdl  
![WSDL non sécurisé](./screens/2025-11-16_16h49_34.png)

- Service sécurisé : http://localhost:8080/services/hello-secure?wsdl  
![WSDL sécurisé](./screens/2025-11-16_17h00_56.png)

## Tests SoapUI
- Créer un projet SoapUI à partir de l’URL du WSDL.
- Tester les opérations `FindPerson` et `SayHello`.

![Requête FindPerson](./screens/2025-11-16_16h50_27.png)
![Requête SayHello](./screens/2025-11-16_16h51_28.png)

Pour le service sécurisé, configurer dans SoapUI un `Outgoing WS-Security Configuration` de type **UsernameToken** avec :
- Username : `student`
- Password : `secret123`

![SoapUI UsernameToken](./screens/2025-11-16_17h09_02.png)

