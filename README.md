# autoriser-lexecution-de-scripts-powershell-non-sign--numeriquement
https://www.it-connect.fr/autoriser-lexecution-de-scripts-powershell/


# https://youtu.be/c30ZuwarBDQ



Autoriser l’exécution de Scripts PowerShell
 22/10/2012  Florian B.  5 Commentaires Powershell
Sommaire [-]

I. Présentation
II. Les 6 modes de sécurité différents
III. Exécutez la console PowerShell
IV. Politique actuelle
V. Modifiez la politique
I. Présentation
Par défaut, la configuration de Windows ne permet pas l'exécution de Scripts PowerShell même si la console est bien présente dans les dernières versions d'OS de Microsoft. Surement dans un soucis de sécurité, et pour ne pas rendre possible l'exécution de ces scripts sur l'utilisateur n'en a pas l'utilité.

Pour autoriser l'exécution des scripts PowerShell sur votre machine, il suffit de modifier la politique de sécurité appliquée en terme d'exécution des scripts.



II. Les 6 modes de sécurité différents
- Restricted : Cette valeur qui est la valeur par défaut, empêche l'exécution de scripts.

- AllSigned : Requiert la signature numérique par un éditeur de l'ensemble des scripts, y compris ceux que vous créez en local sur la machine.

- RemoteSigned : Requiert la signature numérique par un éditeur des scripts téléchargés à partir d'internet.

- Unrestricted : Exécute tous les scripts, mais vous invite à autoriser l'exécution des scripts non signés téléchargés via internet.

- Bypass : Pas de blocage, ni d'avertissements, tout sera exécuté.

- Undefined : Supprime la stratégie d'exécution appliquée, mais pas dans le cas où elle est définie par une stratégie de groupe.
III. Exécutez la console PowerShell
Cliquez sur "Démarrer" puis saisissez "powershell", faites clic droit sur "Windows PowerShell" et cliquez sur "Exécuter en tant qu'Administrateur" pour disposez des privilèges suffisants permettant de modifier le système. Si vous utilisez un système 64 bits, les deux versions de la console apparaîtront.

powershell3

IV. Politique actuelle
La politique de sécurité actuelle doit être "Restricted" qui est la valeur par défaut sous Windows, pour vérifier cela, saisissez la commande PowerShell suivante :

Get-ExecutionPolicy
powershell2
V. Modifiez la politique
Pour pouvoir exécuter des scripts il faut impérativement modifier la politique de sécurité, choisissez le mode qui vous semble le mieux approprié à ce dont vous avez besoin. Pour ma part je choisis le mode "Unrestricted" pour pouvoir exécuter les scripts tout en gardant un minimum de sécurité.

Utilisez la commande suivante :

Set-ExecutionPolicy Unrestricted
Lorsqu'on vous demande de confirmer la modification, indiquez "O" pour Oui et appuyez sur Entrée.
