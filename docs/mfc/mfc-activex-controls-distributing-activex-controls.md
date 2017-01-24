---
title: "Contr&#244;les ActiveX MFC&#160;: distribution de contr&#244;les ActiveX | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetWindowsDirectory"
  - "GetSystemDirectory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "distribuer des contrôles ActiveX MFC"
  - "GetProcAddress (méthode), inscrire des contrôles ActiveX"
  - "GetSystemDirectory (méthode)"
  - "GetWindowsDirectory (méthode)"
  - "installer des contrôles ActiveX"
  - "LoadLibrary (méthode), inscrire des contrôles ActiveX"
  - "contrôles ActiveX MFC, versions ANSI ou Unicode"
  - "contrôles ActiveX MFC, distribuer"
  - "contrôles ActiveX MFC, installer"
  - "contrôles ActiveX MFC, inscrire"
  - "MFC40.DLL"
  - "MFC40U.DLL"
  - "MSVCRT40.dll"
  - "OLEPRO32.DLL"
  - "fichiers redistribuables, contrôles ActiveX MFC"
  - "inscrire des contrôles ActiveX"
  - "inscrire des contrôles"
  - "Registre, inscrire des contrôles"
  - "RegSvr32.exe"
ms.assetid: cd70ac9b-f613-4879-9e81-6381fdfda2a1
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: distribution de contr&#244;les ActiveX
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article décrit plusieurs problèmes liés à la redistribution des contrôles ActiveX :  
  
-   [ANSI ou Versions de Contrôle Unicode](#_core_ansi_or_unicode_control_versions)  
  
-   [Installation des Contrôles ActiveX et DLLs Redistribuables](#_core_installing_activex_controls_and_redistributable_dlls)  
  
-   [Contrôles d'Inscription](#_core_registering_controls)  
  
    > [!NOTE]
    >  Pour plus d'informations sur redistribution des contrôles ActiveX, consultez [Redistribution des contrôles](../data/ado-rdo/redistributing-controls.md).  
  
##  <a name="_core_ansi_or_unicode_control_versions"></a> ANSI ou Versions de Contrôle Unicode  
 Vous devez décider si vous fournissez une version ANSI ou Unicode du contrôle, ou les deux.  Cette décision repose sur les taux de portabilité inhérents à ANSI et les jeux de caractères Unicode.  
  
 Les contrôles ANSI, qui fonctionnent sur tous les systèmes d'exploitation Win32, permettent une portabilité maximale entre les différents systèmes d'exploitation Win32.  Les contrôles Unicode fonctionnent uniquement sur Windows NT \(version 3,51 ou ultérieure\), mais pas sur Windows 95 ou Windows 98.  Si la portabilité est votre principale préoccupation, embarquez les contrôles ANSI.  Si les contrôles sont exécutés uniquement sur Windows NT, vous pouvez embarquer les contrôles Unicode.  Vous pouvez également choisir d'embarquer et de faire installer à votre application la version la plus adéquate pour le système d'exploitation de l'utilisateur.  
  
##  <a name="_core_installing_activex_controls_and_redistributable_dlls"></a> Installation des Contrôles ActiveX et DLLs Redistribuables  
 Le programme d'installation auquel vous fournissez les contrôles ActiveX doit créer un sous\-répertoire spécial du répertoire Windows et installer les fichiers de contrôle .OCX dedans.  
  
> [!NOTE]
>  Utilisez l'API de Windows **GetWindowsDirectory** dans votre programme d'installation pour obtenir le nom du répertoire Windows.  Vous pouvez avoir besoin de dériver le nom du sous\-répertoire à partir du nom de votre société ou de votre produit.  
  
 Le programme d'installation doit installer les fichiers redistribuables DLL nécessaires dans le répertoire système Windows.  Si une DLL quelconque est déjà présente sur l'ordinateur de l'utilisateur, le programme d'installation doit comparer leurs versions avec les versions que vous installez.  Réinstallez un fichier uniquement si son numéro de version est plus grand que le fichier déjà installé.  
  
 Les contrôles ActiveX ne pouvant être utilisés qu'uniquement dans les applications de conteneur OLE, il est inutile de distribuer le jeu complet de la DLL OLE avec vos contrôles.  Vous pouvez supposer que l'application conteneur \(ou le système d'exploitation lui\-même\) possède les DLL standard OLE installés.  
  
##  <a name="_core_registering_controls"></a> Contrôles d'Inscription  
 Avant qu'un contrôle ne puisse être utilisé, les entrées appropriées doivent être créées pour cela dans la base de données d'inscription de Windows.  Certains conteneurs de contrôle ActiveX fournissent un élément de menu pour les utilisateurs pour enregistrer de nouveaux contrôles, mais cette fonctionnalité peut ne pas être disponible dans tous les conteneurs.  Par conséquent, vous pouvez avoir besoin que votre programme d'installation enregistre les contrôles lorsqu'ils sont installés.  
  
 Si vous préférez, vous pouvez écrire votre programme d'installation pour enregistrer le contrôle directement à la place.  
  
 Utilisez l'API Windows **LoadLibrary** pour charger la DLL de contrôle.  Ensuite, utilisez **GetProcAddress** pour obtenir l'adresse de la fonction « DllRegisterServer ».  Enfin, appelez la fonction `DllRegisterServer`.  L'exemple de code suivant présente une méthode possible, où `hLib` enregistre le descripteur de la bibliothèque de contrôle, puis `lpDllEntryPoint` stocke l'adresse de la fonction « DllRegisterServer ».  
  
 [!code-cpp[NVC_MFC_AxCont#16](../mfc/codesnippet/CPP/mfc-activex-controls-distributing-activex-controls_1.cpp)]  
  
 L'avantage d'enregistrer le contrôle directement est que vous n'avez pas besoin d'appeler et de charger un processus séparé \(à savoir, REGSVR32\), ce qui réduit la durée d'installation.  En outre, l'inscription étant un processus interne, le programme d'installation peut gérer les erreurs et les situations imprévues mieux qu'un processus externe.  
  
> [!NOTE]
>  Avant que le programme d'installation n'installe un contrôle ActiveX, il doit appeler **OleInitialize**.  Lorsque le programme d'installation s'est terminé, appelez **OleUnitialize**.  Cela garantit que les DLLs du système OLE sont en état approprié pour enregistrer un contrôle ActiveX.  
  
 Vous devriez enregistrer MFCx0.DLL.  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)