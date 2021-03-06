---
title: La mise à niveau d’un contrôle ActiveX | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [MFC], Internet
- LPK files for Internet controls
- safe for scripting and initialization (controls)
- OLE controls [MFC], upgrading to ActiveX
- CAB files, for ActiveX controls
- Internet applications [MFC], ActiveX controls
- Internet applications [MFC], packaging code for download
- upgrading ActiveX controls
- licensing ActiveX controls
ms.assetid: 4d12ddfa-b491-4f9f-a0b7-b51458e05651
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e40240367d3e8350cee030b2c08dc5a48325e05f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="upgrading-an-existing-activex-control"></a>Mise à niveau d'un contrôle ActiveX
Contrôles ActiveX existant (anciennement contrôles OLE) peut être utilisé sur Internet sans modification. Toutefois, vous souhaiterez modifier des contrôles afin d’améliorer leurs performances. Lorsque vous utilisez votre contrôle sur une page Web, il existe des considérations supplémentaires. Le fichier .ocx et tous les fichiers de prise en charge doivent se trouver sur l’ordinateur cible, ou être téléchargés sur Internet. Cela rend la taille du code et un aspect important de temps de téléchargement. Téléchargements peuvent être empaquetés dans un fichier .cab signé. Vous pouvez marquer votre contrôle comme sécurisés pour les scripts et l’initialisation.  
  
 Cet article traite des sujets suivants :  
  
- [Empaquetage du Code pour le téléchargement](#_core_packaging_code_for_downloading)  
  
- [Le marquage de contrôle sécurisé pour les scripts et l’initialisation](#_core_marking_a_control_safe_for_scripting_and_initializing)  
  
- [À propos des licences](#_core_licensing_issues)  
  
- [Signature de Code](#_core_signing_code)  
  
- [Gestion de la Palette](#_core_managing_the_palette)  
  
- [Niveaux de sécurité du navigateur Internet Explorer et de contrôler le comportement](#_core_internet_explorer_browser_safety_levels_and_control_behavior)  
  
 Vous pouvez également ajouter des optimisations, comme décrit dans [contrôles ActiveX : optimisation](../mfc/mfc-activex-controls-optimization.md). Monikers peuvent être utilisés pour télécharger des propriétés et d’objets BLOB volumineux en mode asynchrone, comme décrit dans [contrôles ActiveX sur Internet](../mfc/activex-controls-on-the-internet.md).  
  
##  <a name="_core_packaging_code_for_downloading"></a> Empaquetage du Code pour le téléchargement  
 Pour plus d’informations sur ce sujet, consultez l’article de la Base de connaissances « Packaging MFC des contrôles pour utilisation sur Internet » (Q167158). Vous pouvez trouver des articles de la Base de connaissances à [ http://support.microsoft.com/support ](http://support.microsoft.com/support).  
  
### <a name="the-codebase-tag"></a>La balise CODEBASE  
 Les contrôles ActiveX sont incorporés dans des pages Web à l’aide de la `<OBJECT>` balise. Le `CODEBASE` paramètre de la `<OBJECT>` balise spécifie l’emplacement à partir duquel télécharger le contrôle. `CODEBASE` peut pointer sur un nombre de différents types de fichiers avec succès.  
  
### <a name="using-the-codebase-tag-with-an-ocx-file"></a>À l’aide de la balise CODEBASE avec un fichier OCX  
  
```  
CODEBASE="http://example.microsoft.com/mycontrol.ocx#version=4,
    70,
    0,
    1086"  
```  
  
 Cette solution télécharge uniquement les fichiers .ocx du contrôle et que requiert que toutes les DLL de prise en charge déjà être installés sur l’ordinateur client. Cela fonctionne pour les contrôles d’Internet Explorer et MFC ActiveX créés avec Visual C++, car Internet Explorer est fourni avec les DLL de prise en charge pour les contrôles de Visual C++. Si un autre navigateur Internet qui est compatible avec les contrôles d’ActiveX est utilisé pour afficher ce contrôle, cette solution ne fonctionnera pas.  
  
### <a name="using-the-codebase-tag-with-an-inf-file"></a>À l’aide de la balise CODEBASE avec un fichier INF  
  
```  
CODEBASE="http://example.microsoft.com/trustme.inf"  
```  
  
 Un fichier .inf contrôle l’installation d’un .ocx et ses fichiers de prise en charge. Cette méthode n’est pas recommandée, car il n’est pas possible de signer un fichier .inf (consultez [de signature de Code](#_core_signing_code) pour les pointeurs sur la signature de code).  
  
### <a name="using-the-codebase-tag-with-a-cab-file"></a>À l’aide de la balise CODEBASE avec un fichier CAB  
  
```  
CODEBASE="http://example.microsoft.com/acontrol.cab#version=1,
    2,
    0,
    0"  
```  
  
 Fichiers CAB sont la méthode recommandée pour les contrôles ActiveX de package qui utilisent MFC. Empaquetage d’un contrôle ActiveX MFC dans un fichier CAB permet à un fichier .inf être inclus pour contrôler l’installation du contrôle ActiveX et des fichiers DLL dépendants (par exemple, les DLL MFC). À l’aide d’un fichier CAB automatiquement compresse le code pour accélérer le téléchargement. Si vous utilisez un fichier .cab pour le téléchargement de composants, il est plus rapide pour signer le fichier .cab tout entier plutôt que chaque composant.  
  
### <a name="creating-cab-files"></a>Création de fichiers CAB  
 Vous pouvez télécharger le Kit de développement du fichier CAB à partir de l’article de la Base de connaissances [310618 : Kit de développement logiciel Microsoft Cabinet](http://go.microsoft.com/fwlink/p/?linkid=148204). Dans ce kit, vous trouverez les outils nécessaires pour créer des fichiers CAB.  
  
 Le fichier cab vers lequel pointe `CODEBASE` doit contenir le fichier .ocx du contrôle ActiveX et un fichier .inf pour contrôler son installation. Vous créez le fichier CAB en spécifiant le nom de votre fichier de contrôle et un fichier .inf. N’incluez pas les fichiers DLL dépendants qui existent déjà sur le système dans le fichier CAB. Par exemple, les DLL MFC sont empaquetées dans un fichier CAB séparé et référencés par le fichier .inf du contrôle.  
  
 Pour plus d’informations sur la création d’un fichier CAB, consultez [création d’un fichier CAB](http://msdn.microsoft.com/en-us/cc52fd09-bdf6-4410-a693-149a308f36a3).  
  
### <a name="the-inf-file"></a>Le fichier INF  
 L’exemple suivant, spindial.inf, répertorie les fichiers de prise en charge et les informations de version nécessitent pour le Spindial MFC contrôler. Notez que l’emplacement de la DLL MFC est un site Web Microsoft. Le fichier mfc42.cab est fourni et signé par Microsoft.  
  
```  
Contents of spindial.inf:  
[mfc42installer]   
file-win32-x86=http://activex.microsoft.com/controls/vc/mfc42.cab   
[Olepro32.dll] - FileVersion=5,
    0,
    4261,
    0  
[Mfc42.dll] - FileVersion=6,
    0,
    8168,
    0  
[Msvcrt.dll] - FileVersion=6,
    0,
    8168,
    0  
```  
  
### <a name="the-object-tag"></a>Le \<objet > balise  
 L’exemple suivant illustre l’utilisation de la `<OBJECT>` balise pour empaqueter l’exemple de contrôle Spindial MFC.  
  
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
  
 Dans ce cas, spindial.cab contiendra deux fichiers, spindial.ocx et spindial.inf. La commande suivante génère le fichier CAB :  
  
```  
C:\CabDevKit\cabarc.exe -s 6144 N spindial.cab spindial.ocx spindial.inf   
```  
  
 Le `-s 6144` paramètre réserve un espace dans le fichier CAB pour la signature de code.  
  
### <a name="the-version-tag"></a>La balise de Version  
 Notez ici que la `#Version` informations spécifiées dans un fichier CAB s’applique au contrôle spécifié par le `CLASSID` paramètre de la `<OBJECT>` balise.  
  
 Selon la version spécifiée, vous pouvez forcer le téléchargement de votre contrôle. Pour des spécifications complètes de la `OBJECT` balise, y compris le `CODEBASE` paramètre, voir le W3C la référence.  
  
##  <a name="_core_marking_a_control_safe_for_scripting_and_initializing"></a> Le marquage de contrôle sécurisé pour les scripts et l’initialisation  
 Contrôles ActiveX utilisés dans les pages Web doivent être marqués comme sécurisé pour le script et l’initialisation s’ils sont en fait sans échec. Un contrôle sécurisé ne sera pas effectuer d’e/s disque ou accéder directement à la mémoire ou les registres d’un ordinateur.  
  
 Contrôles peuvent être marqués comme sécurisés pour les scripts et l’initialisation via le Registre. Modifier `DllRegisterServer` pour ajouter des entrées similaires à ce qui suit pour marquer le contrôle comme sûrs pour l’écriture de scripts et de persistance dans le Registre. Une autre méthode consiste à implémenter `IObjectSafety`.  
  
 Vous allez définir des GUID (Globally Unique Identifiers) pour votre contrôle marquer sécurisé pour les scripts et la persistance. Les contrôles qui peuvent être écrits en toute sécurité contient une entrée de Registre semblable au suivant :  
  
```  
HKEY_CLASSES_ROOT\Component Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}  
```  
  
 Les contrôles qui peuvent être initialisés en toute sécurité à partir des données persistantes sont sûrs pour la persistance avec une entrée de Registre similaire à :  
  
```  
HKEY_CLASSES_ROOT\Component Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}  
```  
  
 Ajouter des entrées similaires à ce qui suit (ID à la place de la classe de substitution de votre contrôle `{06889605-B8D0-101A-91F1-00608CEAD5B3}`) pour associer vos clés à l’ID de classe suivante :  
  
```  
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}   
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}   
```  
  
##  <a name="_core_licensing_issues"></a> À propos des licences  
 Si vous souhaitez utiliser un contrôle sous licence sur une page Web, vous devez vérifier que le contrat de licence permet son utilisation sur Internet et créer un fichier de package de licence (LPK) pour celle-ci.  
  
 Un contrôle ActiveX sous licence chargera pas correctement dans une page HTML si l’ordinateur qui exécute Internet Explorer n’est pas sous licence pour utiliser le contrôle. Par exemple, si un contrôle sous licence a été créé à l’aide de Visual C++, la page HTML à l’aide du contrôle chargera correctement sur l’ordinateur où le contrôle a été généré, mais il ne chargera pas sur un autre ordinateur, sauf si les informations de licence sont incluses.  
  
 Pour utiliser un contrôle ActiveX sous licence dans Internet Explorer, vous devez vérifier le contrat de licence du fournisseur pour vérifier que la licence pour le contrôle autorise :  
  
-   Redistribution  
  
-   Utilisation du contrôle sur Internet  
  
-   Utilisation du paramètre Codebase  
  
 Pour utiliser un contrôle sous licence dans une page HTML sur un ordinateur sans licence, vous devez générer un fichier de package de licence (LPK). Ce fichier contient des licences d’exécution pour les contrôles sous licence dans la page HTML. Ce fichier est généré Lpk_tool. EXE qui est livré avec le SDK ActiveX. Pour plus d’informations, consultez le site Web MSDN à l’adresse [ http://msdn.microsoft.com ](http://msdn.microsoft.com).  
  
#### <a name="to-create-an-lpk-file"></a>Pour créer un fichier LPK  
  
1.  Exécutez LPK_TOOL. EXE sur un ordinateur qui est concédé sous licence pour utiliser le contrôle.  
  
2.  Dans le **outil de création de Package de licence** boîte de dialogue le **contrôles disponibles** zone de liste, sélectionnez chaque licence contrôle ActiveX qui sera utilisé dans la page HTML et cliquez sur **ajouter**.  
  
3.  Cliquez sur **Enregistrer & quitter** et tapez un nom pour le fichier LPK. Cela créera le fichier LPK et fermez l’application.  
  
#### <a name="to-embed-a-licensed-control-on-an-html-page"></a>Pour incorporer un contrôle sous licence sur une page HTML  
  
1.  Modifier votre page HTML. Dans la page HTML, insérez une \<objet > balise pour l’objet Gestionnaire de licences avant toute autre \<objet > balises. Le Gestionnaire de licences est un contrôle ActiveX qui est installé avec Internet Explorer. Son ID de classe est indiqué ci-dessous. Définissez la propriété LPKPath de l’objet Gestionnaire de licences pour le chemin d’accès et le nom du fichier LPK. Vous pouvez avoir qu’un seul fichier LPK par page HTML.  
  
 ```  
 <OBJECT CLASSID = "clsid:5220cb21-c88d-11cf-b347-00aa00a28331">  
 <PARAM NAME="LPKPath" VALUE="relative URL to .LPK file">  
 </OBJECT>  
 ```  
  
2.  Insérer le \<objet > balise pour votre contrôle sous licence après la balise de gestionnaire de licences.  
  
     Par exemple, une page HTML qui affiche le contrôle d’édition par masque Microsoft est indiquée ci-dessous. Le premier identificateur de classe qu'est pour le contrôle de gestionnaire de licences, le deuxième identificateur de classe qu'est pour le contrôle d’édition par masque. Modifiez les balises pour pointer vers le chemin d’accès relatif du fichier d’interactivité que vous avez créé précédemment et ajoutez une balise d’objet, y compris l’ID de classe de votre contrôle.  
  
3.  Insérer le \<EMBED > attribut pour le fichier LPK, si vous utilisez le module complémentaire NCompass ActiveX.  
  
     Si votre contrôle peut être affiché sur les autres Active les navigateurs d’ordinateurs compatibles : par exemple, Netscape utilisant le module complémentaire NCompass ActiveX — vous devez ajouter le \<EMBED > syntaxe comme illustré ci-dessous.  
  
 ```  
 <OBJECT CLASSID="clsid:5220cb21-c88d-11cf-b347-00aa00a28331">  
 <PARAM NAME="LPKPath" VALUE="maskedit.lpk">  
 
 <EMBED SRC = "maskedit.LPK">  
 
 </OBJECT>  
 <OBJECT CLASSID="clsid:C932BA85-4374-101B-A56C-00AA003668DC" WIDTH=100 HEIGHT=25>  
 </OBJECT>  
 ```  
  
 Pour plus d’informations sur les licences de contrôle, consultez [contrôles ActiveX : licences des contrôles ActiveX](../mfc/mfc-activex-controls-licensing-an-activex-control.md).  
  
##  <a name="_core_signing_code"></a> Signature de Code  
 Signature de code est conçue pour identifier la source du code, et pour garantir que le code n’a pas changé depuis qu’il a été signé. En fonction des paramètres de sécurité du navigateur, les utilisateurs peuvent être avertis avant le téléchargement du code. Les utilisateurs peuvent choisir d’approuver certains détenteurs de certificats ou les sociétés, dans lequel cas le code signé par les personnes approuvées sera téléchargé sans avertissement. Code est signé numériquement pour éviter toute falsification.  
  
 Assurez-vous que le code final est signé afin que votre contrôle peut être téléchargé automatiquement sans afficher les messages d’avertissement de niveau de confiance. Pour plus d’informations sur la signature de code, consultez la documentation sur Authenticode dans le SDK ActiveX et [signature d’un fichier CAB](http://msdn.microsoft.com/en-us/04d8b47a-8f1c-4b54-ab90-730fcdc03747).  
  
 En fonction de l’approbation et navigateur au niveau paramètres de sécurité, un certificat peut être affiché pour identifier la personne ou la société signataire. Si le niveau de sécurité est none ou si le propriétaire du certificat du contrôle signé est approuvé, un certificat ne sera pas affiché. Consultez [niveaux de sécurité du navigateur Internet Explorer et de contrôler le comportement](#_core_internet_explorer_browser_safety_levels_and_control_behavior) pour plus d’informations sur la façon dont le paramètre de sécurité du navigateur déterminent si votre contrôle est téléchargé et un certificat est affiché.  
  
 Code de garanties de signature numérique n’a pas changé, car il a été signé. Un hachage du code est effectué et incorporé dans le certificat. Ce hachage est comparé ultérieurement avec un hachage du code pris après le téléchargement du code, mais avant son exécution. Les sociétés telles que Verisign peuvent fournir des clés publiques et privées nécessaires pour signer le code. Le SDK ActiveX est livré avec MakeCert, un utilitaire de création de certificats de test.  
  
##  <a name="_core_managing_the_palette"></a> Gestion de la Palette  
 Les conteneurs déterminent la palette et le rendre disponible comme une propriété ambiante, **DISPID_AMBIENT_PALETTE**. Un conteneur (par exemple, Internet Explorer) choisit une palette qui est utilisée par tous les contrôles ActiveX sur une page pour déterminer leur propre palette. Cela empêche l’affichage scintillement et présente une apparence cohérente.  
  
 Un contrôle peut substituer `OnAmbientPropertyChange` pour gérer la notification des modifications apportées à la palette.  
  
 Un contrôle peut substituer `OnGetColorSet` pour retourner un jeu pour dessiner la palette de couleurs. Conteneurs utilisent la valeur de retour pour déterminer si un contrôle est compatible avec la palette.  
  
 Sous les directives OCX 96, un contrôle doit toujours réaliser sa palette en arrière-plan.  
  
 Les conteneurs plus anciens qui n’utilisent pas la propriété ambiante palette enverra `WM_QUERYNEWPALETTE` et `WM_PALETTECHANGED` messages. Un contrôle peut substituer `OnQueryNewPalette` et `OnPaletteChanged` pour gérer ces messages.  
  
##  <a name="_core_internet_explorer_browser_safety_levels_and_control_behavior"></a> Niveaux de sécurité du navigateur Internet Explorer et de contrôler le comportement  
 Un navigateur propose des options pour le niveau de sécurité configurable par l’utilisateur. Étant donné que les pages Web peuvent contenir un contenu actif qui peut endommager l’ordinateur d’un utilisateur, navigateurs autorisent l’utilisateur à sélectionner des options pour le niveau de sécurité. Selon la façon dont un navigateur implémente des niveaux de sécurité, un contrôle ne peut pas être téléchargé à tout ou affiche un certificat ou un message d’avertissement pour autoriser l’utilisateur de choisir au moment de l’exécution ou non télécharger le contrôle. Le comportement de contrôles ActiveX à des niveaux de sécurité élevé, moyen et faible dans Internet Explorer est répertorié ci-dessous.  
  
### <a name="high-safety-mode"></a>Mode haute sécurité  
  
-   Les contrôles non signés ne seront pas téléchargées.  
  
-   Contrôles signés affichent un certificat si non approuvés (un utilisateur peut choisir une option pour approuver systématiquement le code à partir de ce propriétaire du certificat par la suite).  
  
-   Seuls les contrôles marqués comme sécurisés seront contiennent des données persistantes et/ou scriptable.  
  
### <a name="medium-safety-mode"></a>Mode de sécurité moyen  
  
-   Contrôles non signés affichent un avertissement avant de télécharger.  
  
-   Contrôles signés affichent un certificat si non fiables.  
  
-   Contrôles non marqués comme sécurisés affiche un avertissement.  
  
### <a name="low-safety-mode"></a>Mode de sécurité faible  
  
-   Les contrôles sont téléchargés sans avertissement.  
  
-   Scripts et la persistance surviennent sans avertissement.  
  
## <a name="see-also"></a>Voir aussi  
 [Tâches de programmation Internet MFC](../mfc/mfc-internet-programming-tasks.md)   
 [Base de programmation Internet MFC](../mfc/mfc-internet-programming-basics.md)   
 [Contrôles ActiveX MFC : gestion des licences d’un contrôle ActiveX](../mfc/mfc-activex-controls-licensing-an-activex-control.md)

