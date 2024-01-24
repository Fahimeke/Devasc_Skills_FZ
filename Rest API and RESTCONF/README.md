# Devasc_Skills_FZ




Taaknaam: RESTCONF

Taakvoorbereiding:
Voorafgaand aan deze taak heb ik ervoor gezorgd dat:

Mijn virtuele DEVASC-machine en virtuele CSR1Kv-router operationeel waren.
Ik vertrouwd was met de curl-opdrachten van pagina 8 tot 10 op de webpagina RESTCONF Protocol.
Mijn DEVASC-machine en CSR1Kv-router waren bereikbaar en correct waren geconfigureerd.
Taakimplementatie:

Testen van curl-opdrachten:

Ik heb de curl-instructies van pagina 8 tot 10 op de webpagina RESTCONF Protocol getest.
Transformeren van curl-opdrachten naar Python-code:

Ik heb drie curl-opdrachten omgezet in Python-code met behulp van RESTCONF.
python
Copy code
import requests
from requests.auth import HTTPBasicAuth

# Voorbeeld 1: GET-operatie
url = 'https://your-router-ip/restconf/data/ietf-interfaces:interfaces'
response = requests.get(url, auth=HTTPBasicAuth('your-username', 'your-password'))
print(response.json())  # Voer de JSON-response uit

# Voorbeeld 2: POST-operatie
url = 'https://your-router-ip/restconf/data/ietf-interfaces:interfaces/interface=eth0'
payload = '{"ietf-interfaces:interface": {"name": "eth0", "description": "New Interface"}}'
response = requests.post(url, auth=HTTPBasicAuth('your-username', 'your-password'), data=payload)
print(response.status_code)  # Controleer de statuscode van de response

# Voorbeeld 3: DELETE-operatie
url = 'https://your-router-ip/restconf/data/ietf-interfaces:interfaces/interface=eth1'
response = requests.delete(url, auth=HTTPBasicAuth('your-username', 'your-password'))
print(response.status_code)  # Controleer de statuscode van de response
Oplossen van fouten met "logging monitor":

In geval van fouten heb ik een snelle oplossing toegepast om "logging monitor" te activeren via de Cisco IOS CLI van mijn virtuele router.
Screenshots:

Ik heb screenshots gemaakt om het succes van mijn acties aan te tonen.
Opslaan van Python-code op GitHub:

Ik heb de Python-code opgeslagen op mijn GitHub-repository voor toekomstige referentie.
Probleemoplossing:

Bij fouten heb ik "logging monitor" geactiveerd via de Cisco IOS CLI van de virtuele router om aanvullende informatie te verkrijgen.
Verificatie van de taak:

Succesvolle uitvoering van Python-code:

Ik heb ervoor gezorgd dat de Python-code zonder fouten werd uitgevoerd.
Screenshots:

De gemaakte screenshots bevestigen het succes van de uitgevoerde acties.
GitHub-opslag:

Ik heb de Python-code op mijn GitHub-repository opgeslagen en de link verstrekt.