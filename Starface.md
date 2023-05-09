

<details>
<summary>Update 09.05.2023</summary>

```
Features:	
WICHTIGE ALLGEMEINE HINWEISE
Leitungen ohne Authentifizierung UND deren Leitungsnamen ein Leerzeichen enthalten bauen ​​keine Gespräche auf, bspw. bei dem Betrieb eines SBC (siehe Known Issue)​.
Bitte stellen Sie sicher, dass Sie keine selbst-signierte Zertifikate verwenden. Zertifikate vom Typ 'self-signed' werden nicht mehr akzeptiert und müssen gegebenenfalls ausgetauscht werden. STARFACE 8 erfordert zwingend valide Zertifikate für die verschlüsselte Telefonie (für Snom, Yealink und Gigaset). Die Definition valider Zertifikate ist abhängig vom Hersteller
für Snom kann man sich beispielsweise an Mozilla orientieren
Zertifikate von 'Let's Encrypt' sind beispielsweise soweit bekannt valide. Prüfung und Austausch können vor oder nach dem Update erfolgen, aber unbedingt vor der Aktivierung einer Telefon-Verschlüsselung. Die Zertifikate der STARFACE Clouds sind geprüft und valide, hier besteht kein Handlungsbedarf Ihrerseits.
Die bisherige STARFACE App für Windows in der Version 7.3 ist weiterhin kompatibel mit der STARFACE 8.
Die neue App für Windows (Version 8.x) erfordert zwingend die STARFACE 8.

Mindestanforderungen
Bitte beachten Sie, dass bei einem Update der STARFACE auf die Version 8 der freie Speicherplatz mindestens 6 GB beträgt, zuzüglich der doppelten Größe des zu importierenden Backups.
Virtualisierte STARFACE-Installationen erfordern mindestens 2 GB Arbeitsspeicher.

Update-/Migrationspfad
Das Update von STARFACE 7.0 und höher auf STARFACE 8 kann, wie bisher gewohnt als normales Update über das Webinterface installiert werden, und erfordert keine Neuinstallation.
Updates von STARFACE Clouds nehmen Sie bitte direkt über das Cloud-Management im Partnerportal vor. Dadurch können Sie auch direkt von STARFACE 6 auf STARFACE 8 aktualisieren.
Das Update von STARFACE 6 auf STARFACE 8 ist über den Admin-Bereich nicht direkt möglich: Der Migrationspfad führt, wie bisher über die STARFACE 7, wofür wir ein spezielles Modul anbieten, welches das Updateprozedere bei Appliances übernimmt.
Virtualisierte STARFACE-Installationen müssen manuell neuinstalliert werden. Einzelheiten dazu finden Sie in unserer Knowledge Base.
Backups von älteren Versionen (z.B. STARFACE 6.7) können wie gewohnt ebenfalls in die STARFACE 8 importiert werden.

VOR dem Update
Wir empfehlen, vor dem Update die Ruflisten, Faxlisten, Voicemails und Rufaufnahmen mit dem Modul 'STARFACE Archivierung' zu archivieren.
Wir empfehlen, in allen Modulen mit vollqualifizierten Rufnummern zu arbeiten.
Prüfen Sie bitte vor der Installation, ob das siptrunk.de-Profil Ihres Anbieters aktualisiert wurde.
Mit der STARFACE 8 sind potentielle Anpassungen bei Modulen erforderlich. Wir empfehlen vor einem Update zu prüfen, ob für die verwendeten Module eine aktuelle, 8.0-kompatible Version vorliegt. Informieren Sie sich hierzu bei den jeweiligen Modulpartner.

NACH dem Update
Bitte aktualisieren Sie Ihre STARFACE Apps auf die jeweilige neueste Version, dies gilt insbesondere für die neue STARFACE App für Windows. Ältere Versionen der STARFACE Apps (Windows, MacOS, Android & iOS) sind nicht vollständig kompatibel mit STARFACE 8.
Wenn Sie ausschließlich eine STARFACE Connect Leitung verwenden, stellen Sie in den Einstellungen sicher, dass Sie die höchste Routing-Priorität verwenden.
Bitte prüfen Sie bereits installierte Module auf neuere Versionen und aktualisieren Sie diese nach dem Update.
Aktivierte Verschlüsselungen von Snom-Telefonen werden durch ein Update auf die STARFACE 8 automatisch deaktiviert und müssen im Nachgang manuell im Admin-Bereich neu gesetzt werden.

FEATURES & VERBESSERUNGEN
Anpassung der Präsenzstatus-Logik/Non-STARFACE XMPP-Clients:
Sämtliche Status-Updates vom Typ 'unavailable' werden in Openfire nun ignoriert, es sei denn, es handelt sich dabei um die letzte bekannte Session des Nutzer-Accounts:
Ein Benutzer ist immer online, wenn einer oder mehrere seiner XMPP Clients online sind.
Ein Benutzer ist nur dann offline und 'unavailable' für Chat, wenn kein XMPP Client online ist.
Ein Benutzer ist so lange online, wie dieser in der Mobile App angemeldet ist und die App aktiv ist
d.h. der Benutzer sich nicht abmeldet oder die App schließt. Achtung: Wenn die App in iOS in den Hintergrund wandert, gilt diese als offline.
Bei der Verwendung von Nicht-Starface XMPP-Clients, werden geänderte Avatar-Bilder nicht mehr an andere Clients übertragen. Die Bilder müssen dafür jetzt über die Nutzer-Einstellungen im Webinterface oder einen Starface-Client erfolgen.
Erweiterte verschlüsselte Telefonie und Provisionierung:
Yealink-Telefone unterstützen nun verschlüsselte Auto-Provisionierung, STARFACE-Menüs und Telefonie über SRTP und TLS (SIPS).
Snom-Telefone unterstützen nun zusätzlich verschlüsselte Auto-Provisionierung und STARFACE-Menüs und alle Nicht-Legacy Snom-Telefone verschlüsselte Telefonie über SRTP und TLS (SIPS).
Gigaset N870 und N670 unterstützen nun verschlüsselte Auto-Provisionierung, STARFACE-Menüs und Telefonie über SRTP und TLS (SIPS).
Backup and Restore:
Neues Backup-Format, für deutlich schnellere Backups und Wiederherstellungen und zuverlässigere Recovery-Prozesse im Fehlerfall.
Backups, die mit älteren STARFACE-Versionen erstellt wurden, werden weiterhin unterstützt und können wie gewohnt importiert werden.
Fehlermeldungen des Backups erscheinen jetzt nicht nur im 'error.log' sondern auch im 'backup.log'.
Neue Log-Datei 'update.log': Die bisherigen Logs in '/var/log/starface-update/' werden nun in einer Log-Datei unter '/var/log/starface/update.log.' aggregiert und angezeigt.
Neue REST-Schnittstelle 'server/backups' für die Erstellung, Ausführung und Wiederherstellung von Backups sowie für die Abfrage des aktuellen Prozess-Status (siehe 'REST API').
Endgeräte:
Neu: Grandstream HT812 wird nun unterstützt.
Gigaset N720: Aktualisierung auf v117
Yealink T58V/T56A: Aktualisierung auf 58.86.150.1
Yealink T58W: Aktualisierung auf 150.86.150.2
Yealink VP59: Aktualisierung auf 91.86.150.2
Anpassung: Auf den Snom-Telefonen D385, D717, D735 und D785 wird im Ruhezustand für einen eingeloggten Benutzer nun dessen STARFACE-Benutzerbild angezeigt.
Technologie:
Integration der Asterisk Realtime Architektur, d.h. Umstellung von Konfigurationsdateien auf Datenbank für SIP-Peers, für eine verbesserte Bearbeitung von SIP-Reloads und dadurch Entlastung des Asterisks und Verbesserung der Gesamt-Performance.
Aktualisierung von Asterisk auf Version 16.30.0
Aktualisierung von Java auf Version JDK 17 (LTS)
REST API:
Neuer Endpunkt zum Herunterladen eines getriggerten Backups: 'GET /server/backups/files/{backupJobId}'. Erfordert die Berechtigung 'Admin_MISC'. Der Response enthält einen Hex-kodierten SHA256-Hash, welcher optional für den Restore verwendet werden kann.
Neuer Endpunkt zur Abfrage des aktuellen Status eines laufenden Backup- oder Restore-Prozesses 'GET /server/backups/state/{backupJobId}', keine spezifische Berechtigung erforderlich.
Neuer Endpunkt zum Triggern eines Backups mit der übermittelten Konfiguration 'PUT /server/backups/actions/run', erfordert die Berechtigung 'Admin_MISC'.
Neuer Endpunkt zum Triggern eines Restore-Prozesses mit dem übermittelten Backup 'PUT /server/backups/actions/restore', erfordert die Berechtigung 'Admin_MISC'. Es kann zusätzlich ein SHA256-Hash für eine serverseitige Verifizierung mitgegeben werden.
Der Endpunkt '/users/{userId}/managedConferences/{conferenceId}' gibt nun eine 'ForbiddenException' statt 'UnauthorizedException' für GET/PUT/DELETE zurück, wenn der ausführende Benutzer nicht Besitzer der Konferenz oder Administrator ist.
Der Endpunkt '/users/{userId}/phonenumberconfig/phonenumbers/delete' verwendet nun die Methode 'DELETE' zum Löschen. Die bisherige POST-Methode wurde als deprecated markiert.
UCI API:
Neuer UCI-Endpunkt für Module-Instanzen: Ein Benutzer mit den richtigen Berechtigungen kann alle konfigurierten Modulinstanzen anfordern, ein ausgewähltes Set abonnieren und Aktualisierungen erhalten, sobald Änderungen auftreten. Der Benutzer kann zudem den Status jeder Modulinstanz umschalten, unabhängig davon, ob diese abonniert ist oder nicht. Es werden eine der beiden folgenden Berechtigungen für den Zugriff benötigt: 'Administration' und 'Tasten'.
Der Endpunkt '/users/{userId}/managedConferences/{conferenceId}' gibt nun eine 'ForbiddenException' statt 'UnauthorizedException' für GET/PUT/DELETE zurück, wenn der ausführende Benutzer nicht Besitzer der Konferenz oder Administrator ist.
Der Endpunkt '/users/{userId}/phonenumberconfig/phonenumbers/delete' verwendet nun die Methode 'DELETE' zum Löschen. Die bisherige POST-Methode wurde als deprecated markiert.
Administration:
Im Systemstatus der Administration wurde eine neue Schaltfläche 'Alle löschen' hinzugefügt, mit der nun alle Meldungen auf einmal gelöscht werden können.
Neue Log-Datei 'status.log': enthält Informationen zu Änderungen durch Benutzer im Systemstatus der Administration (bspw. das Löschen von Meldungen).
Die neue Log-datei 'update.log' unter '/var/log/starface/' aggregiert die bisherigen Protokolldateien in '/var/log/starface-update/' aus der Phase 3 der STARFACE-Updates.
LDAP/Estos MetaDirectory:
Mit dem estos MetaDirectory 5 als externes Adressbuch für die STARFACE, können nun benutzerspezifische Lese-Zugriffsrechte vergeben werden. Für die zwingend erforderliche Synchronisierung der bestehenden Benutzer-Accounts empfehlen wir die Verwendung eines Microsoft Active Directory. Bei der Verwendung von Email-Adressen als User-ID müssen für Gruppen zusätzlich separate Email-Adressen erstellt werden. Alternativ kann die Login-/Account-ID verwendet werden.
Monitoring:
Ein lokales Monitoring des PBX-Systems wurde integriert (Prometheus).
Das lokale Monitoring erfordert einen SSH-Zugang.
Bugfixes:	
Rufliste:
Besetzt-Weiterleitungen zur Voicemailbox generieren nach Abweisen des Anrufs nun korrekte Einträge in der Rufliste.
Bei einem angenommenen Gruppenanruf wird das Feld 'übernommen von' nun korrekt befüllt. [Call#7601947] [Call#7706171] [Call#7779028] [Call#7748713] [Call#7778699] [Call#7798049] [Call#7786250]
Gruppenanrufe werden nun korrekt in der Rufliste dargestellt, wenn der Benutzer den Call via iFMC angenommen hat. [Call#7216027] [Call#7722694]
Call Handling:
Die BLFs im Call Manager der WEB-UI werden wieder korrekt dargestellt.
Die Rufübernahme über Sternwahl '*8' funktioniert nur noch mit der Nummer des Angerufenen.
iQueue:
Es wurde ein Fehler behoben, welcher in bestimmten Situationen dazu führen konnte, dass nach der Anruf-Annahme durch einen Agenten, alle anderen Agenten einer iQueue blockiert wurden. [Call#7130785]
Endgeräte:
Das N510 funktioniert nun wieder, wenn die PBX auf 'Französisch' eingestellt ist. [Call#7140740] [Call#7131028] [Call#7134799] [Call#7153462]
Die unbenutzte Rufliste des Yealink CP960 wurde entfernt.
Die DECT-Mobilteile des Snom M900 können nun über deren Menüs oder durch ein langes Drücken der Taste '#' stumm geschaltet werden. [CALL#7622417]
Adressbuch und LDAP:
Ein Fehler beim Wechsel des Ordners während der Erstellung eines neuen Kontaktes wurde behoben.
Die Buttons für Import und Hinzufügen eines Eintrags im LDAP-Adressbuch sind nun nicht mehr sichtbar, wenn das Verzeichnis schreibgeschützt ist.
Einträge mit bestimmten Sonderzeichen, welche über LDAP geladen werden, werden nun korrekt dargestellt.
Administration:
Die Menüpunkte 'Systemstatus' und 'STARFACE Neon/Connect' der Administration sind jetzt nur noch für Benutzer mit der Berechtigung 'Admin_MISC' sichtbar. [Call#7654656]
Die Telefonkonfiguration (Softphone/SIP Account) für eine STARFACE App wird beim Löschen eines Benutzerkontos nun ebenfalls entfernt. Dies gilt auch für Updates respektive Imports von Backups, welche nicht mehr zugewiesenen Softphone-Konfigurationen aufweisen.
Lange Fehlermeldungen bei der Konfiguration des LDAP-Adressbuchs werden nun wieder korrekt im Dialogfenster dargestellt.
Die Zielrufnummern von Weiterleitungen werden nun korrekt in der WEB-UI gespeichert, wenn eine Voicemailbox als Ziel ausgewählt ist.
Umleitungen werden nun ohne Fehlermeldung gespeichert, wenn keine Voicemail und Zielrufnummer angegeben wurde.
Fehlermeldungen für Weiterleitungen zeigen nun den Umleitungstyp und die betroffene Rufnummer korrekt an.
Fehlende Log-Dateien führen nun nicht mehr zu einem Absturz der Log-UI im Administrationsbereich 'Server: Log-Dateien'. [Call#7703077] [Call#7783173]
Änderungen von Funktionstasten können wieder beliebig oft gespeichert und an ein Telefon übertragen werden.
Doppelte Einträge in den Leitungskonfigurationen führen nicht mehr zu Fehlern beim Systemstart.
Der Anlagen-Neustart wird nicht mehr verzögert, wenn Verbindungsversuche zur STARFACE Neon API fehlschlagen. [Call#7725594]
REST API:
Die Telefonieoptionen 'DND' und 'Anklopfen' eines Benutzers können nun wieder über 'PUT /users//phoneconfig' ordnungsgemäß gesetzt werden, wenn dem Benutzer kein Telefon zugewiesen ist.
Module API:
Der Building Block 'SetCaller' wird nun wieder korrekt aus dem Rufnummernstamm ermittelt. [Call#7186800]
Für die Modulfunktion 'CallPhoneNumber' funktionieren 'caller number' und 'ringing duration' nun wieder korrekt. [Call#7107093] [Call#7180142] [Call#7581660]
```

</details>


#### warum werden bei einem Telefonat 2 Aktive Kanäle angezeigt?
```
Zur Zeit aktive Rufkanäle:	2
```
Jede Aktive Verbindung wird immer mit 2 Rufkanälen angezeigt.
## Shortcuts
[Tastenkombinationen](https://knowledge.starface.de/display/SWD/Tastenkombinationen+am+Telefon)
