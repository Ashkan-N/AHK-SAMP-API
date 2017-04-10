# AHK-SAMP-API
#### By Ashkan-N
### API für AutoHotkey von Grand Theft Auto San Andreas Multiplayer

Dies ist eine API für AutoHotkey von GTA SAMP.
Hiermit wird es einem Programmierer vereinfacht in AutoHotkey zu arbeiten.
Diese API stellt dem Programmierer mehrere Funktionen verfügbar um die Arbeit zu optimieren.

### Funktionen
```autohotkey
###############################################################################################################################
# SAMP-Funktionen:                                                                                                            #
# --------------------------------------------------------------------------------------------------------------------------- #
#                                                                                                                             #
#     - IsSAMPAvailable()                         Prüft, ob man in den Chat schreiben kann & ob GTA geladen ist               #
#     - IsInChat()                                Prüft, ob der Spieler gerade chattet oder in einem Dialog ist               #
#     - GetPlayerName()                           Liest den Namen des Spielers aus                                            #
#     - GetPlayerId()                             Liest die ID des Spielers aus                                               #
#     - SendChat(wText)                           Sendet eine Nachricht oder einen Befehl direkt an den Server                #
#     - AddChatMessage(wText)                     Fügt eine Zeile in den Chat ein (nur für den Spieler sichtbar)              #
#     - ShowGameText(wText, dwTime, dwTextstyle)  Zeigt einen Text inmitten des Bildschirmes an                               #
#     - PlayAudioStream(wUrl)                     Spielt einen "Audio Stream" ab                                              #
#     - StopAudioStream()                         Stoppt den aktuellen Audio Stream                                           #
#     - GetChatLine(Line, ByRef Output)           Liest die eingestellte Zeile aus,                                           #
#                                                 Optionale Parameter (timestamp=0, color=0)                                  #
#     - BlockChatInput()                          Eine Funktion, um Messages zum Server zu blockieren                         #
#     - UnBlockChatInput()                        Eine Funktion, um Messages zum Server zu entblockieren                      #
#                                                                                                                             #
# --------------------------------------------------------------------------------------------------------------------------- #
#                                                                                                                             #
#     - GetServerName()                           Ermittelt den Server-Namen (HostName)                                       #
#     - GetServerIp()                             Ermittelt die IP des Servers                                                #
#     - GetServerPort()                           Ermittelt den Port des Servers                                              #
#     - CountOnlinePlayers()                      Ermittelt wie viele Spieler auf dem Server Online sind.                     #
#                                                                                                                             #
# --------------------------------------------------------------------------------------------------------------------------- #
#                                                                                                                             #
#     - GetWeatherId()                            Gibt die aktuelle Wetter ID zurück                                          #
#     - GetWeatherName()                          Gibt den aktuellen Wetternamen zurück                                       #
#                                                                                                                             #
# --------------------------------------------------------------------------------------------------------------------------- #
#                                                                                                                             #
#     - PatchRadio()                              (interner stuff)                                                            #
#     - UnPatchRadio()                            (interner stuff)                                                            #
#                                                                                                                             #
###############################################################################################################################
# SAMP Dialog Funktionen (v0.3.7):                                                                                            #
# --------------------------------------------------------------------------------------------------------------------------- #
#                                                                                                                             #
#     - IsDialogOpen()                            Prüft, ob gerade ein Dialog angezeigt wird (gibt true oder false zurück)    #
#     - GetDialogStyle()                          Liest den Typ des (zuletzt) angezeigten Dialogs aus (0-5)                   #
#     - GetDialogId()                             Liest die ID des (zuletzt) angezeigten Dialogs aus (auch vom Server)        #
#     - SetDialogId(id)                           Setzt die ID des (zuletzt) angezeigten Dialogs                              #
#     - GetDialogIndex()                          Liest die (zuletzt) ausgewählte Zeile des Dialogs aus                       #
#     - GetDialogCaption()                        Liest die Überschrift des (zuletzt) angezeigten Dialogs aus                 #
#     - GetDialogText()                           Liest den Text des (zuletzt) angezeigten Dialogs aus (auch bei Listen)      #
#     - GetDialogLineCount()                      Liest die Anzahl der Zeilen/Items des (zuletzt) angezeigten Dialogs aus     #
#     - GetDialogLine(index)                      Liest die Zeile an der Stelle [index] mittels GetDialogText aus             #
#     - GetDialogLines__()                          Liest die Zeilen mittels GetDialogText aus (gibt ein Array zurück)        #
#     - IsDialogButton1Selected()                 Prüft, ob Button1 des Dialogs ausgewählt ist                                #
#     - GetDialogStructPtr()                      Liest den Base Pointer zur Dialogstruktur aus (intern genutzt)              #
#                                                                                                                             #
#     - ShowDialog(style, caption, text,          Zeigt einen Dialog an (nur lokal)                                           #
#                  button1, button2, id)                                                                                      #
#                                                                                                                             #
###############################################################################################################################
# Extra-Player-Funktionen:                                                                                                    #
# --------------------------------------------------------------------------------------------------------------------------- #
#                                                                                                                             #
#     - GetTargetPed(dwPED)                       Zeigt die PED-ID, des Spielers, auf den man zielt.                          #
#     - GetPedById(dwId)                          Zeigt die PED-Id zu der Id.                                                 #
#     - GetIdByPed(dwId)                          Zeigt die Id der PED-Id.                                                    #
#     - GetStreamedInPlayersInfo()                Zeigt Informationen über die gestreamten Spieler.                           #
#     - CallFuncForAllStreamedInPlayers()         Führt bestimmte Funktionen, für die gestreamten Spieler aus.                #
#     - GetDist(pos1,pos2)                        Rechnet den Abstand zwischen zwei Positionen aus.                           #
#     - GetClosestPlayerPed()                     Zeigt die PED-ID, des Spielers, der am nahesten zu einem steht.             #
#     - GetClosestPlayerId()                      Zeigt die Id, des Spielers, der am nahesten zu einem steht.                 #
#     - GetPedCoordinates(dwPED)                  Zeigt die Koordinaten, der PED-ID.                                          #
#     - GetTargetPosById(dwId)                    Zeigt die Position, zu der angegebenen Id.                                  #
#     - GetTargetPlayerSkinIdByPed(dwPED)         Zeigt den Skin, zu der angegebenen PED-ID.                                  #
#     - GetTargetPlayerSkinIdById(dwId)           Zeigt den Skin, zu der angegebenen ID.                                      #
#     - CalcScreenCoords(fX, fY, fZ)              WorldToScreen Funktion                                                      #
#                                                                                                                             #
###############################################################################################################################
# Extra-Player-Fahrzeug-Funktionen:                                                                                           #
# --------------------------------------------------------------------------------------------------------------------------- #
#                                                                                                                             #
#     - GetVehiclePointerByPed(dwPED)             Zeigt die PED-ID des Autos.                                                 #
#     - GetVehiclePointerById(dwId)               Zeigt die PED-ID des Autos.                                                 #
#     - IsTargetInAnyVehicleByPed(dwPED)          Zeigt ob der Spieler in einem Auto ist.                                     #
#     - IsTargetInAnyVehicleById(dwId)            Zeigt ob der Spieler in einem Auto ist.                                     #
#     - GetTargetVehicleHealthByPed(dwPED)        Zeigt ob der Spieler in einem Auto ist.                                     #
#     - GetTargetVehicleHealthById(dwId)          Zeigt ob der Spieler in einem Auto ist.                                     #
#     - GetTargetVehicleTypeByPed(dwPED)          Ermittelt den FahrzeugTyp (Auto, LKW etc.)                                  #
#     - GetTargetVehicleTypeById(dwId)            Ermittelt den FahrzeugTyp (Auto, LKW etc.)                                  #
#     - GetTargetVehicleModelIdByPed(dwPED)       Ermittelt die FahrzeuGmodell ID                                             #
#     - GetTargetVehicleModelIdById(dwId)         Ermittelt die Fahrzeugmodell ID                                             #
#     - GetTargetVehicleModelNameByPed(dwPED)     Ermittelt den Fahrzeugmodell Namen                                          #
#     - GetTargetVehicleModelNameById(dwId)       Ermittelt den Fahrzeugmodell Namen                                          #
#     - GetTargetVehicleLightStateByPed(dwPED)    Ermittelt den Lichtzustand des Autos                                        #
#     - GetTargetVehicleLightStateById(dwId)      Ermittelt den Lichtzustand des Autos                                        #
#     - GetTargetVehicleLockStateByPed(dwPED)     Ermittelt ob das Auto auf oder zu ist                                       #
#     - GetTargetVehicleLockStateById(dwId)       Ermittelt ob das Auto auf oder zu ist                                       #
#     - GetTargetVehicleColor1ByPed(dwPED)        Ermittelt die 1. Color-ID des Autos                                         #
#     - GetTargetVehicleColor1ById(dwId)          Ermittelt die 1. Color-ID des Autos                                         #
#     - GetTargetVehicleColor2ByPed(dwPED)        Ermittelt die 2. Color-ID des Autos                                         #
#     - GetTargetVehicleColor2ById(dwId)          Ermittelt die 2. Color-ID des Autos                                         #
#     - GetTargetVehicleSpeedByPed(dwPED)         Ermittelt die Geschwindigkeit des Autos                                     #
#     - GetTargetVehicleSpeedById(dwId)           Ermittelt die Geschwindigkeit des Autos                                     #
#                                                                                                                             #
###############################################################################################################################
# Scoreboard-Funktionen:                                                                                                      #
# --------------------------------------------------------------------------------------------------------------------------- #
#                                                                                                                             #
#     - GetPlayerScoreById(dwId)                  Zeigt den Score zu der Id                                                   #
#     - GetPlayerPingById(dwId)                   Zeigt den Ping zu der Id                                                    #
#     - GetPlayerNameById(dwId)                   Zeigt den Namen zu der Id                                                   #
#     - GetPlayerIdByName(wName)                  Zeigt die Id zu dem Namen                                                   #
#     - UpdateScoreboardDataEx()                  Aktualisiert Scoreboard Inhalte (wird implizit aufgerufen)                  #
#     - UpdateOScoreboardData()                   Aktualisiert Scoreboard Inhalte (wird implizit aufgerufen)                  #
#     - IsNPCById(dwId)                           Zeigt an ob die ID ein NPC                                                  #
#                                                                                                                             #
###############################################################################################################################
# Spielerfunktionen:                                                                                                          #
# --------------------------------------------------------------------------------------------------------------------------- #
#                                                                                                                             #
#     - GetPlayerHealth()                         Ermittelt die HP des Spielers                                               #
#     - GetPlayerArmor()                          Ermittelt den Rüstungswert des Spielers                                     #
#     - GetPlayerInteriorId()                     Ermittelt die Interior ID wo der Spieler ist                                #
#     - GetPlayerSkinId()                         Ermittelt die Skin ID des Spielers                                          #
#     - GetPlayerMoney()                          Ermittelt den Kontostand des Spielers (nur GTA Intern)                      #
#     - GetPlayerWanteds()                        Ermittelt die Wantedanzahl des Spielers (nur bis 6 Wanteds)                 #
#     - GetPlayerWeaponId()                       Ermittelt die Waffen ID des Spielers                                        #
#     - GetPlayerWeaponName()                     Ermittelt den Namen, der Waffe des Spielers                                 #
#     - GetPlayerState()                          Ermittelt den "Status" des Spielers (Zu Fuss, Fahrer, Tot)                  #
#     - GetPlayerMapPosX()                        Ermittelt die X-Position auf der Map im Menu                                #
#     - GetPlayerMapPosY()                        Ermittelt die Y-Position auf der Map im Menu                                #
#     - GetPlayerMapZoom()                        Ermittelt den Zoom auf der Map im Menu                                      #
#     - IsPlayerFreezed()                         Ermittelt ob der Spieler freezed ist                                        #
#                                                                                                                             #
###############################################################################################################################
# Fahrzeugfunktionen:                                                                                                         #
# --------------------------------------------------------------------------------------------------------------------------- #
#                                                                                                                             #
#     - IsPlayerInAnyVehicle()                    Ermittelt, ob sich der Spieler in einem Fahrzeug befindet                   #
#     - GetVehicleHealth()                        Ermittelt die HP des Fahrzeugs, in dem der Spieler sitzt                    #
#     - IsPlayerDriver()                          Ermittelt ob der Spieler Fahrer des Autos ist                               #
#     - GetVehicleType()                          Ermittelt den FahrzeugTyp (Auto, LKW etc.)                                  #
#     - GetVehicleModelId()                       Ermittelt die Fahrzeugmodell ID                                             #
#     - GetVehicleModelName()                     Ermittelt den Fahrzeugmodell Namen                                          #
#     - GetVehicleLightState()                    Ermittelt den Lichtzustand des Autos                                        #
#     - GetVehicleEngineState()                   Ermittelt den Motorzustand des Autos                                        #
#     - GetVehicleLockState()                     Ermittelt ob das Auto auf oder zu ist                                       #
#     - GetVehicleColor1()                        Ermittelt die 1. Farbe ID des Autos                                         #
#     - GetVehicleColor2()                        Ermittelt die 2. Farbe ID des Autos                                         #
#     - GetVehicleSpeed()                         Ermittelt die Geschwindigkeit des Autos                                     #
#     - GetPlayerRadiostationId()                 Ermittelt die Radiostation-ID des Autos                                     #
#     - GetPlayerRadiostationName()               Ermittelt den Radiostation-Namen des Autos                                  #
#     - GetVehicleNumberPlate()                   Ermittelt das Kennzeichen des Autos                                         #
#                                                                                                                             #
###############################################################################################################################
# Standpunktbestimmung:                                                                                                       #
# --------------------------------------------------------------------------------------------------------------------------- #
#                                                                                                                             #
#     - GetPlayerCoordinates()                    Ermittelt die aktuelle Position (Koordinaten)                               #
#     - GetPlayerPos(X, Y, Z)                     siehe oben drüber                                                           #
#                                                                                                                             #
# --------------------------------------------------------------------------------------------------------------------------- #
#                                                                                                                             #
#     - InitZonesAndCities()                      Initialisiert eine Liste aller Standartgebiete                              #
#                                                 (Voraussetzung für die folgenden Funktionen dieser Kategorie)               #
#     - CalculateZone(X, Y, Z)                    Bestimmt die Zone (= Stadtteil) aus den geg. Koordinaten                    #
#     - CalculateCity(X, Y, Z)                    Bestimmt die Stadt aus den geg. Koordinaten                                 #
#     - GetCurrentZonecode()                      Ermittelt die aktulle Zone in Kurzform (Entfernt, da es nicht funktioniert) #
#     - AddZone(Name, X1, Y1, Z1, X2, Y2, Z2)     Fügt eine Zone zum Index hinzu                                              #
#     - AddCity(Name, X1, Y1, Z1, X2, Y2, Z2)     Fügt eine Stadt zum Index hinzu                                             #
#     - IsPlayerInRangeOfPoint(X, Y, Z, Radius)   Bestimmt ob der Spieler in der Nähe der Koordinaten ist                     #
#     - IsPlayerInRangeOfPoint2D(X, Y, Radius)    Bestimmt ob der Spieler in der Nähe der Koordinaten ist                     #
#     - GetPlayerZone()                                                                                                       #
#     - GetPlayerCity()                                                                                                       #
#                                                                                                                             #
###############################################################################################################################
# Sonderfunktionen:                                                                                                           #
# --------------------------------------------------------------------------------------------------------------------------- #
#                                                                                                                             #
#     - getServerStatus(INADDR, PORT)             Zeigt den Status eines Servers an                                           #
#     - getAttacker(bReset := false)              Ermittelt den letzten Angreifer                                             #
#     - UnlockFPS()                               Entfernt das FPS-Limit                                                      #
#     - FormatNumber(number)                      Formatiert eine Nummer                                                      #
#     - PlayerInput(text)                         Öffnet eine Spielereingabe im Chat                                          #
#     - DownloadToString(url, encoding = "utf-8") Downloaded eine Textdatei als String                                        #
#     - stringMath(string)                        Berechnet eine Mathematische Aufgabe                                        #
#     - getPageSize()                             Chatline Anzahl auslesen                                                    #
#     - SetPercentageHealthAndArmor(toggle)       Lebens- und Rüstungsanzeige in Prozent anzeigen                             #
#     - SetChatLine(line, string)                 Inhalt einer bestimmten Zeile ändern                                        #
#     - UrlDownloadToVar(URL, ByRef Result, UserAgent = "", Proxy = "", ProxyBypass = "") URL als Variable                    #
#                                                                                                                             #
###############################################################################################################################
# Sonstiges:                                                                                                                  #
# --------------------------------------------------------------------------------------------------------------------------- #
#                                                                                                                             #
#     - AntiCrash()                               Hilft gegen das abstürzen bei Warningscodes                                 #
#                                                                                                                             #
###############################################################################################################################
# Speicherfunktionen (intern genutzt):                                                                                        #
# --------------------------------------------------------------------------------------------------------------------------- #
#                                                                                                                             #
#     - checkHandles()                                                                                                        #
#     - refreshGTA()                                                                                                          #
#     - refreshSAMP()                                                                                                         #
#     - refreshMemory()                                                                                                       #
#     - getPID(szWindow)                                                                                                      #
#     - openProcess(dwPID, dwRights)                                                                                          #
#     - closeProcess(hProcess)                                                                                                #
#     - getModuleBaseAddress(sModule, dwPID)                                                                                  #
#     - readString(hProcess, dwAddress, dwLen)                                                                                #
#     - readFloat(hProcess, dwAddress)                                                                                        #
#     - readDWORD(hProcess, dwAddress)                                                                                        #
#     - readMem(hProcess, dwAddress, dwLen=4, type="UInt")                                                                    #
#     - writeString(hProcess, dwAddress, wString)                                                                             #
#     - writeRaw(hProcess, dwAddress, data, dwLen)                                                                            #
#     - Memory_ReadByte(process_handle, address)                                                                              #
#     - callWithParams(hProcess, dwFunc, aParams, bCleanupStack = true)                                                       #
#     - virtualAllocEx(hProcess, dwSize, flAllocationType, flProtect)                                                         #
#     - virtualFreeEx(hProcess, lpAddress, dwSize, dwFreeType)                                                                #
#     - createRemoteThread(hProcess, lpThreadAttributes, dwStackSize, lpStartAddress, lpParameter, dwCreationFlags,           #
#                          lpThreadId)                                                                                        #
#     - __ansiToUnicode(sString, nLen = 0)                                                                                    #
#     - __unicodeToAnsi(wString, nLen = 0)                                                                                    #
#                                                                                                                             #
###############################################################################################################################
```
### Credits
*** SAMP UDF R16 ***
SAMP Version: 0.3.7

> Written by Chuck_Floyd 
https://github.com/FrozenBrain

> Modified by Suchty112
https://github.com/Suchty112

> Modified by: paul-phoenix
https://github.com/paul-phoenix

> Modified by: Agrippa1994
https://github.com/agrippa1994

> Modified by: RawDev and ELon

> Refactoring by: Peek
https://github.com/pkfln

> Modified by: Ashkan-N
https://github.com/Ashkan-N
_____
