---
title: "Mise &#224; niveau d&#39;un contr&#244;le ActiveX | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles ActiveX (C++), Internet"
  - "fichiers CAB, pour les contrôles ActiveX"
  - "applications Internet (C++), contrôles ActiveX"
  - "applications Internet (C++), empaqueter le code pour le téléchargement"
  - "licences des contrôles ActiveX"
  - "fichiers LPK pour les contrôles Internet"
  - "contrôles OLE (C++), mettre à niveau vers ActiveX"
  - "sûrs pour l'écriture de scripts et l'initialisation (contrôles)"
  - "mettre à niveau des contrôles ActiveX"
ms.assetid: 4d12ddfa-b491-4f9f-a0b7-b51458e05651
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Mise &#224; niveau d&#39;un contr&#244;le ActiveX
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les contrôles ActiveX \(anciennement contrôles OLE\) existants peuven être utilisés sur Internet sans modification.  Toutefois, vous pouvez vouloir modifier des contrôles pour améliorer leurs performances.  Lors de l'utilisation de votre contrôle sur une page Web, il y a des considérations supplémentaires.  Le fichier .ocx et les fichiers de prise en charge doivent se trouver sur l'ordinateur cible ou être téléchargés sur Internet.  Cela fait que le nombre et le temps de téléchargement des instructions est un aspect important.  Les téléchargements peuvent être emballés dans un fichier .cab signé.  Vous pouvez marquer le contrôle comme sûr de script, et comme sécurisé pour initialiser.  
  
 Cette rubrique traite des sujets suivants :  
  
-   [Empaqueter du code pour le téléchargement](#_core_packaging_code_for_downloading)  
  
-   [Marquer un contrôle comme sur pour scriptage et initialisation](#_core_marking_a_control_safe_for_scripting_and_initializing)  
  
-   [Problèmes de licences](#_core_licensing_issues)  
  
-   [Signature du code](#_core_signing_code)  
  
-   [Gérer la palette](#_core_managing_the_palette)  
  
-   [Niveaux de sécurité de navigateur Internet Explorer et comportement du contrôle](#_core_internet_explorer_browser_safety_levels_and_control_behavior)  
  
 Vous pouvez également ajouter des optimisations, comme décrit dans [Contrôles ActiveX : Optimisation](../mfc/mfc-activex-controls-optimization.md).  Des monikers peuvent être utilisés pour télécharger des propriétés et des objets BLOB de façon asynchrone, comme décrit dans [Contrôles ActiveX Internet](../mfc/activex-controls-on-the-internet.md).  
  
##  <a name="_core_packaging_code_for_downloading"></a> Empaqueter du code pour le téléchargement  
 Pour plus d'informations sur cette rubrique, consultez l'article de la Base de connaissances « empaquetage des contrôles MFC pour utilisation sur Internet » \(Q167158\).  Vous trouverez les articles de Base de connaissances sur le CD\-ROM de la bibliothèque MSDN ou à l'adresse [http:\/\/support.microsoft.com\/support](http://support.microsoft.com/support).  
  
### L'indicateur CODEBASE  
 Les contrôles ActiveX sont incorporés dans les pages Web à l'aide de l'indicateur `<OBJECT>`.  Le paramètre `CODEBASE` de l'indicateur `<OBJECT>` spécifie l'emplacement à partir duquel télécharger du contrôle.  `CODEBASE` peut pointer à plusieurs autres types de fichiers avec succès.  
  
### L'utilisation de l'indicateur CODEBASE avec un fichier d'OCX  
  
```  
CODEBASE="http://example.microsoft.com/mycontrol.ocx#version=4,70,0,1086"  
```  
  
 Cette solution ne télécharge que le fichier .ocx du contrôle, et nécessite toutes les DLL de prise en charge déjà installées sur l'ordinateur client.  Ceci fonctionne pour Internet Explorer et les contrôles ActiveX MFC construits avec Visual C\+\+, car Internet Explorer est fourni avec les DLL de prise en charge pour les contrôles Visual C\+\+.  Si un autre navigateur Internet qui supporte les contrôles ActiveX est utilisé pour afficher ce contrôle, cette solution ne s'exécutera pas.  
  
### L'utilisation de l'indicateur CODEBASE avec un fichier INF  
  
```  
CODEBASE="http://example.microsoft.com/trustme.inf"  
```  
  
 Un fichier .inf contrôlera l'installation d'un .ocx et ses fichiers de prise en charge.  Cette méthode n'est pas recommandée car il n'est pas possible de signer un fichier .inf \(voir [Signature de code](#_core_signing_code) pour des bases sur la signature de code\).  
  
### Utilisation de l'indicateur CODEBASE avec un fichier CAB  
  
```  
CODEBASE="http://example.microsoft.com/acontrol.cab#version=1,2,0,0"  
```  
  
 Les fichiers CAB sont la méthode recommandée d'empaqueter les contrôles ActiveX qui utilisent MFC.  Empaqueter un contrôle ActiveX MFC dans un fichier CAB permet à un fichier .inf d'être inclus pour contrôler l'installation du contrôle ActiveX et de toutes les DLL nécessaires \(tels que les DLL MFC\).  L'utilisation d'un fichier CAB compresse automatiquement le code pour un chargement plus rapide.  Si vous utilisez un fichier .cab pour le téléchargement d'un composant, il est plus rapide de signer le fichier .cab entier que chaque composant spécifique.  
  
### Créer des fichiers CAB  
 Vous pouvez télécharger le kit de développement CAB à partir de l'article de la Base de Connaissances [310618 : Kit de développement CAB de Microsoft](http://go.microsoft.com/fwlink/?LinkId=148204).  Dans le kit, vous trouverez les outils requis pour construire des fichiers CAB.  
  
 Le fichier CAB référencé par `CODEBASE` devrait contenir le fichier .ocx pour votre contrôle ActiveX et un fichier .inf pour contrôler son installation.  Vous créez le fichier CAB en spécifiant le nom de votre fichier de contrôle et d'un fichier .inf.  N'incluez pas les DLL dépendants qui peuvent exister sur le système dans ce fichier CAB.  Par exemple, les DLL MFC sont emballés dans un fichier CAB séparé et désignés par le fichier contrôle .inf.  
  
 Pour plus d'informations sur la création d'un fichier CAB, consultez [Créer un fichier CAB](http://msdn.microsoft.com/fr-fr/cc52fd09-bdf6-4410-a693-149a308f36a3).  
  
### Le fichier INF  
 L'exemple suivant, spindial.inf, répertorie les fichiers de prise en charge et les informations de version requis pour le contrôle MFC Spindial.  Notez que l'emplacement des fichiers DLL MFC est un site Web Microsoft.  Le mfc42.cab est fourni et signé par Microsoft.  
  
```  
Contents of spindial.inf:  
[mfc42installer]   
file-win32-x86=http://activex.microsoft.com/controls/vc/mfc42.cab   
[Olepro32.dll] - FileVersion=5,0,4261,0  
[Mfc42.dll] - FileVersion=6,0,8168,0  
[Msvcrt.dll] - FileVersion=6,0,8168,0  
```  
  
### L'indicateur \<OBJECT\>  
 L'exemple suivant illustre l'utilisation de l'indicateur `<OBJECT>` pour emballer le contrôle exemple MFC Spindial.  
  
```  
<OBJECT ID="Spindial1" WIDTH=100 HEIGHT=51  
  CLASSID="CLSID:06889605-B8D0-101A-91F1-00608CEAD5B3"  
  CODEBASE="http://example.microsoft.com/spindial.cab#Version=1,0,0,001">  
    <PARAM NAME="_Version" VALUE="65536">  
    <PARAM NAME="_ExtentX" VALUE="2646">  
    <PARAM NAME="_ExtentY" VALUE="1323">  
    <PARAM NAME="_StockProps" VALUE="0">  
    <PARAM NAME="NeedlePosition" VALUE="2">  
</OBJECT>  
```  
  
 Dans ce cas, spindial.cab contient deux fichiers, spindial.ocx et spindial.inf.  La commande suivante générera le fichier CAB :  
  
```  
C:\CabDevKit\cabarc.exe -s 6144 N spindial.cab spindial.ocx spindial.inf   
```  
  
 Le paramètre `–s 6144` réserve de l'espace dans le fichier CAB pour la signature de code.  
  
### L'indicateur de version  
 Notez ici que les informations de `#Version` spécifiées dans un fichier CAB s'appliquent au contrôle spécifié par le paramètre `CLASSID` de l'indicateur `<OBJECT>`.  
  
 Selon la version, vous pouvez forcer le téléchargement du contrôle.  Pour les fonctionnalités complètes de l'indicateur `OBJECT` y compris le paramètre `CODEBASE`, consultez la référence W3C.  
  
##  <a name="_core_marking_a_control_safe_for_scripting_and_initializing"></a> Marquer un contrôle comme sur pour scriptage et initialisation  
 Les contrôles ActiveX utilisés dans les pages Web doivent être marquées comme sûr pour scriptage et initialisation s'ils sont en fait sécurisés.  Un contrôle sécurisé n'effectue pas de tâche E\/S de disque ou d'accès à la mémoire ou les registres d'un ordinateur.  
  
 Les contrôles peuvent être marqués comme sûr pour scriptage et initialisation via le Registre.  Modifiez `DllRegisterServer` pour ajouter des entrées semblables aux suivantes pour marquer le contrôle comme sûr pour scriptage et persistance dans le Registre.  Une autre méthode consiste à implémenter `IObjectSafety`.  
  
 Vous définirez des GUID \(identificateurs globaux uniques\) pour le contrôle pour le marquer comme sécurisé pour scriptage et persistance.  Les contrôles qui peuvent être écrits en toute sécurité contiendront une entrée de Registre comme suit :  
  
```  
HKEY_CLASSES_ROOT\Component Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}  
```  
  
 Les contrôles qui peuvent être initialisés sans risque pour les données persistantes sont marqués sûrs pour la persistance avec une entrée de Registre similaire à :  
  
```  
HKEY_CLASSES_ROOT\Component Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}  
```  
  
 Ajoutez des entrées semblables aux suivantes \(en remplaçant l'ID de classe de votre contrôle au lieu de `{06889605-B8D0-101A-91F1-00608CEAD5B3}`\) pour associer les clés avec l'ID de classe suivant :  
  
```  
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}   
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}   
```  
  
##  <a name="_core_licensing_issues"></a> Problèmes de licences  
 Si vous souhaitez utiliser un contrôle autorisé dans une page Web, vous devez vérifier que le contrat de licence permet son utilisation sur Internet et créer un fichier de package de licence \(LPK\) pour celui\-ci.  
  
 Un contrôle ActiveX autorisé ne chargera pas correctement dans une page HTML si l'ordinateur exécutant Internet Explorer n'est pas autorisé à utiliser le contrôle.  Par exemple, si un contrôle autorisé est établi à l'aide de Visual C\+\+, la page HTML utilisant le contrôle charge correctement sur l'ordinateur où le contrôle a été créé, mais ne chargera pas sur un autre ordinateur à moins que les informations de licences soit incluses.  
  
 Pour utiliser un contrôle ActiveX autorisé dans Internet Explorer, vous devez vérifier le contrat de licence du fournisseur pour vérifier que la licence du contrôle permet :  
  
-   Redistribution  
  
-   Utilisation du contrôle sur Internet  
  
-   Utilisation du paramètre Codebase  
  
 Pour utiliser un contrôle sous license dans une page HTML sur un ordinateur sans license, vous devez générer un fichier de package de licence \(LPK\).  Le fichier LPK contient des licences d'exécution pour les contrôles autorisés dans la page HTML.  Ce fichier est généré via LPK\_TOOL.EXE fourni avec le SDK ActiveX.  Pour plus d'informations, consultez cette page sur le site MSDN à [http:\/\/msdn.microsoft.com](http://msdn.microsoft.com).  
  
#### Pour créer un fichier LPK  
  
1.  Exécutez LPK\_TOOL.EXE sur un ordinateur qui est autorisé à utiliser le contrôle.  
  
2.  Dans la boîte de dialogue **License Package Authoring Tool**, dans la zone de liste **Available Controls**, sélectionnez chaque contrôle ActiveX sous license qui est utilisé dans la page HTML et cliquez sur **Add**.  
  
3.  Cliquez sur **Save & Exit** et tapez un nom pour le fichier LPK.  Cela crée le fichier LPK et clôturera l'application.  
  
#### Pour inclure un contrôle autorisé dans une page HTML  
  
1.  Modifiez votre page HTML.  Dans la page HTML, insérez un indicateur \<OBJECT\> pour l'objet de gestionnaire de licence avant les autres indicateurs \<OBJECT\>.  Le gestionnaire de licence est un contrôle ActiveX qui est installé avec Internet Explorer.  L'ID de classe est indiqué ci\-dessous.  Définissez la propriété LPKPath de l'objet gestionnaire de licence au chemin d'accès et au nom du fichier LPK.  Il ne peut exister qu'un seul fichier LPK par page HTML.  
  
    ```  
    <OBJECT CLASSID = "clsid:5220cb21-c88d-11cf-b347-00aa00a28331">  
        <PARAM NAME="LPKPath" VALUE="relative URL to .LPK file">  
    </OBJECT>  
    ```  
  
2.  Insérez l'indicateur \<OBJECT\> pour le contrôle sous license après l'indicateur du gestionnaire de licence.  
  
     Par exemple, une page HTML qui affiche le contrôle Microsoft Masked Edit est affichée ci\-dessous.  Le premier ID de classe est pour le contrôle du gestionnaire de licence, le deuxième ID de classe est pour le contrôle Masked Edit.  Modifiez les indicateurs pour indiquer le chemin d'accès relatif du fichier .lpk que vous avez créé précédemment, puis ajoutez un indicateur OBJECT incluant l'ID de classe pour le contrôle.  
  
3.  Insérez l'attribut \<EMBED\> pour votre fichier LPK, si vous utilisez le plug\-in ActiveX NCompass.  
  
     Si le contrôle peut être affiché dans d'autres navigateurs compatibles Active \(par exemple, Netscape avec le plug\-in ActiveX NCompass — vous devez ajouter la syntaxe \<EMBED\> comme indiqué ci\-dessous.  
  
    ```  
    <OBJECT CLASSID="clsid:5220cb21-c88d-11cf-b347-00aa00a28331">  
        <PARAM NAME="LPKPath" VALUE="maskedit.lpk">  
  
        <EMBED SRC = "maskedit.LPK">  
  
    </OBJECT>  
    <OBJECT CLASSID="clsid:C932BA85-4374-101B-A56C-00AA003668DC" WIDTH=100 HEIGHT=25>  
    </OBJECT>  
    ```  
  
 Pour plus d'informations sur les licences des contrôles, consultez [Contrôles ActiveX : Licences des contrôles ActiveX](../mfc/mfc-activex-controls-licensing-an-activex-control.md).  
  
##  <a name="_core_signing_code"></a> Signature du code  
 La signature du code est conçue pour identifier la source du code, et vérifier que le code n'a pas changé depuis qu'il a été signé.  Selon les paramètres de sécurité de navigateur, les utilisateurs peuvent être prévenus avant que le code soit téléchargé.  Les utilisateurs peuvent choisir de faire confiance à certaines sociétés ou propriétaires de certificat, auquel cas le code signé par les éditeurs approuvés sera téléchargé sans avertissement.  Le code est signé numériquement pour éviter de le falsifier.  
  
 Vérifiez que votre code final est signé afin que le contrôle soit automatiquement téléchargé sans afficher les messages d'avertissement de confiance.  Pour plus d'informations sur la façon de signer du code, consultez la documentation sur Authenticode dans le SDK ActiveX et consultez [Signer un fichier CAB](http://msdn.microsoft.com/fr-fr/04d8b47a-8f1c-4b54-ab90-730fcdc03747).  
  
 Selon les paramètres de confiance et de sécurité du navigateur, un certificat peut être affiché pour identifier la personne ou la société ayant signé.  Si le niveau de sécurité est nul, ou si le propriétaire du certificat signé du contrôle est approuvé, le certificat ne sera pas affiché.  Voir [Niveaux de sécurité de navigateur Internet Explorer et comportement des contrôles](#_core_internet_explorer_browser_safety_levels_and_control_behavior) pour plus d'informations sur la façon dont les paramètres de sécurité de navigateur déterminent si le contrôle est téléchargé et si un certificat est affiché.  
  
 La signature numérique de code garantit que le code n'a pas été modifié depuis qu'il a été signé.  Un hachage du code est pris et incorporé au certificat.  Le hachage est ensuite comparé à un hachage du code pris après le téléchargement mais avant son exécution.  Les sociétés telles que Verisign peuvent fournir une clé privée et des clés publiques nécessaires pour signer du code.  Le SDK ActiveX est fourni avec MakeCert, un utilitaire pour créer des certificats de test.  
  
##  <a name="_core_managing_the_palette"></a> Gérer la palette  
 Les conteneurs déterminent la palette et la mettent à disposition en tant que propriété ambiante, **DISPID\_AMBIENT\_PALETTE**.  Un conteneur \(par exemple, Internet Explorer\) choisit une palette utilisée par tous les contrôles ActiveX dans la page pour déterminer leur propre palette.  Cela empêche le scintillement et présente un affichage cohérent.  
  
 Un contrôle peut remplacer `OnAmbientPropertyChange` pour traiter la notification des modifications à la palette.  
  
 Un contrôle peut remplacer `OnGetColorSet` pour retourner un jeu de couleurs pour dessiner la palette.  Les conteneurs utilisent la valeur de retour pour déterminer si un contrôle utilise la palette.  
  
 Sous les instructions d'OCX 96, un contrôle doit toujours réaliser la palette en arrière\-plan.  
  
 Les conteneurs plus anciens qui n'utilisent pas la propriété ambiante de palette enverront des messages `WM_QUERYNEWPALETTE` et `WM_PALETTECHANGED`.  Un contrôle peut remplacer `OnQueryNewPalette` et `OnPaletteChanged` pour traiter les messages.  
  
##  <a name="_core_internet_explorer_browser_safety_levels_and_control_behavior"></a> Niveaux de sécurité de navigateur Internet Explorer et comportement du contrôle  
 Un navigateur a des options pour le niveau de sécurité, configurables par l'utilisateur.  Les pages Web peuvent contenir du contenu actif qui pourrait mettre en péril l'ordinateur d'un utilisateur, les navigateurs permettent aux utilisateurs de sélectionner des options pour le niveau de sécurité.  Selon la façon dont un navigateur implémente des niveaux de sécurité, un contrôle peut ne pas être téléchargé du tout, ou afficher un certificat ou un message d'avertissement pour permettre à l'utilisateur de choisir au moment de l'exécution s'il faut télécharger le contrôle.  Le comportement des contrôles ActiveX dans les niveaux haut, moyen et bas de sécurité dans Internet Explorer est répertorié ci\-dessous.  
  
### Mode haute sécurité  
  
-   Les contrôles non signés ne sont pas téléchargés.  
  
-   Les contrôles signés affichent un certificat s'ils ne sont pas dignes de confiance \(un utilisateur peut choisir une option pour toujours faire confiance au code du propriétaire du certificat à partir de maintenant\).  
  
-   Seuls les contrôles marqués comme sûr ont des données persistantes et\/ou sont scriptables.  
  
### Mode de sécurité intermédiaire  
  
-   Les contrôles non signés affichent un avertissement avant de télécharger.  
  
-   Les contrôles signés affichent un certificat si non approuvés.  
  
-   Les contrôles non marqués comme sûr affichent un avertissement.  
  
### Mode de sécurité basse  
  
-   Les contrôles sont téléchargés sans avertissement.  
  
-   Le scriptage et la persistance se produisent sans avertissement.  
  
## Voir aussi  
 [Tâches de programmation Internet MFC](../mfc/mfc-internet-programming-tasks.md)   
 [Éléments fondamentaux relatifs à la programmation Internet MFC](../mfc/mfc-internet-programming-basics.md)   
 [Contrôles ActiveX MFC : gestion des licences d'un contrôle ActiveX](../mfc/mfc-activex-controls-licensing-an-activex-control.md)