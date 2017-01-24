---
title: "Portage d&#39;UNIX vers Win32 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "APIs [C++], porting to Win32"
  - "migration [C++]"
  - "porting to Win32 [C++]"
  - "porting to Win32 [C++], from UNIX"
  - "UNIX [C++], porting to Win32"
  - "Win32 applications [C++], migrating from UNIX"
  - "Windows API [C++], migrating from UNIX"
ms.assetid: 3837e4fe-3f96-4f24-b2a1-7be94718a881
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Portage d&#39;UNIX vers Win32
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour effectuer la migration d'applications d'UNIX vers Windows, vous avez le choix entre plusieurs options :  
  
-   Utiliser des bibliothèques UNIX pour porter les applications d'UNIX vers Win32  
  
-   Porter des applications d'UNIX vers Win32 en mode natif  
  
-   Exécuter les applications UNIX sous Windows à l'aide du sous\-système POSIX  
  
## Bibliothèques UNIX  
 Une option généralement envisagée par les programmeurs UNIX consiste à utiliser des bibliothèques tierces de type UNIX pour compiler leur code UNIX comme un exécutable Win32.  Plusieurs bibliothèques commercialisées \(et au moins une dans le domaine public\) offrent cette possibilité.  Certaines applications le proposent en tant qu'option.  Ces bibliothèques de portage présentent l'avantage de réduire le travail de portage initial.  Leur principal inconvénient, pour un logiciel soumis à la concurrence, est que le portage Win32 en mode natif d'une application est généralement plus rapide et incontestablement plus riche en fonctionnalités.  Il peut s'avérer difficile pour l'application de sortir de son shell UNIX si elle doit effectuer des appels Win32 pour mieux exploiter la puissance de Windows.  
  
 La liste suivante indique les ressources Microsoft et tierces disponibles pour le portage et la prise en charge de la migration d'UNIX vers Visual C\+\+ :  
  
### Guides de migration d'UNIX  
 Le manuel « UNIX Custom Application Migration Guide » fournit une aide technique sur la migration du code de l'environnement UNIX vers l'environnement Win32.  
  
 [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=95428](http://go.microsoft.com/fwlink/?LinkId=95428)  
  
 Le manuel « Unix Migration Project Guide » vient compléter le manuel « UNIX Custom Application Migration Guide » en proposant une aide détaillée sur la migration de projets majeurs d'UNIX vers Win32.  Ce guide fournit des conseils relatifs aux problèmes susceptibles de se produire aux différentes étapes de la migration d'un projet.  Il peut être téléchargé à l'adresse suivante :  
  
 [http:\/\/go.microsoft.com\/fwlink\/?linkid\=20012](http://go.microsoft.com/fwlink/?linkid=20012)  
  
### Microsoft Windows Services for UNIX \(SFU\)  
 Microsoft Windows Services for UNIX \(SFU\) fournit une gamme complète de services multiplateforme pour intégrer Windows dans les environnements UNIX existants.  Ces services permettent le partage de fichiers, l'administration et l'accès à distance, la synchronisation de mot de passe et la gestion d'annuaires communs. Ils fournissent aussi un ensemble d'utilitaires communs et un shell.  
  
 [Windows Services for UNIX](http://www.microsoft.com/downloads/details.aspx?FamilyID=896c9688-601b-44f1-81a4-02878ff11778&displaylang=en)  
  
### InteropSystems.com  
 [http:\/\/www.interopsystems.com\/](http://www.interopsystems.com/)  
  
 Il s'agit du site d'une société tierce qui fournit des solutions logicielles de prise en charge du portage d'UNIX vers Win32.  
  
### Site web C\+\+ Boost  
 [http:\/\/boost.sourceforge.net\/regression\-logs\/](http://boost.sourceforge.net/regression-logs/)  
  
 [http:\/\/boost.sourceforge.net\/boost\-build2\/](http://boost.sourceforge.net/boost-build2/)  
  
## Portage d'applications UNIX directement vers Win32  
 Une autre option consiste à porter les applications UNIX directement vers Win32.  Grâce aux bibliothèques C\/C\+\+ ANSI et aux bibliothèques du compilateur C disponibles dans le commerce, la plupart des appels système classiques sur lesquels s'appuient les applications UNIX sont possibles dans les applications Win32.  
  
 Le modèle de sortie des applications **stdio** ne nécessite aucune modification, car les API de console Win32 simulent ce modèle **stdio**, et il existe des versions de *curses* qui utilisent les API de console Win32.  Pour plus d'informations, voir [SetConsoleCursorPosition](http://msdn.microsoft.com/library/windows/desktop/ms686025).  
  
 Les applications qui utilisent des sockets Berkeley nécessitent très peu de modifications pour fonctionner comme des applications Win32.  L'interface Windows Sockets a été conçue pour garantir la portabilité avec les sockets BSD, moyennant quelques modifications mineures, comme indiqué dans les sections d'introduction de la spécification WinSock.  
  
 Windows prend en charge le RPC conforme à DCE, ce qui rend les applications basées sur RPC facilement utilisables.  Voir [Fonctions RPC](http://msdn.microsoft.com/library/windows/desktop/aa378623).  
  
 L'une des principales différences réside dans le modèle de processus.  UNIX utilise le processus **fork**, ce qui n'est pas le cas de Win32.  En fonction de l'utilisation de **fork** et de la base de code, vous avez le choix entre ces deux API Win32 : **CreateProcess** et `CreateThread`.  Une application UNIX qui duplique plusieurs copies d'elle\-même peut être modifiée dans Win32 de façon à avoir plusieurs processus ou un seul processus avec plusieurs threads.  Si plusieurs processus sont utilisés, différentes méthodes d'IPC sont disponibles pour établir la communication entre les processus \(et éventuellement pour mettre à jour le code et les données du nouveau processus par rapport au parent, si la fonctionnalité assurée par **fork** est nécessaire\).  Pour plus d'informations sur IPC, voir [Communications entre processus](http://msdn.microsoft.com/library/windows/desktop/aa365574).  
  
 Les modèles graphiques UNIX et Windows sont très différents.  UNIX utilise l'interface GUI du système X Window, alors que Windows utilise l'interface GDI.  Les deux sont similaires d'un point de vue conceptuel, mais il n'existe pas de mappage simple entre l'API X et l'API GDI.  Toutefois, une prise en charge OpenGL est disponible pour faire migrer des applications OpenG UNIX.  Il existe en outre des clients X et des serveurs X pour Windows.  Pour plus d'informations sur GDI, voir [Contextes de périphérique](http://msdn.microsoft.com/library/windows/desktop/dd183553).  
  
 Les applications UNIX de base, y compris de nombreuses applications CGI, peuvent normalement être portées facilement vers Visual C\+\+ sous Windows.  Des fonctions comme **open**, `fopen`, **read**, **write** et d'autres sont disponibles dans la bibliothèque Runtime Visual C\+\+.  En outre, un mappage un\-à\-un est possible entre les API C UNIX et les API Win32 : **open** et **CreateFile**, **read** et **ReadFile**, **write** et **WriteFile**, `ioctl` et **DeviceIOControl**, **close** et **CloseFile**, etc.  
  
## Sous\-système POSIX sous Windows  
 Une autre option étudiée par les programmeurs UNIX est celle du sous\-système POSIX sous Windows.  Toutefois, seule la version 1003.1 de POSIX, qui est l'unique version ayant été normalisée au lancement de Windows NT, est prise en charge.  Depuis, la demande pour une extension de ce sous\-système a été faible, la plupart des applications ayant été converties en Win32.  Le système 1003.1 présente un intérêt limité pour les applications complètes, car de nombreuses fonctionnalités lui font défaut \(notamment celles de la version 1003.2, la prise en charge réseau, etc.\).  Les applications complètes exécutées sur le sous\-système POSIX sous Windows n'ont pas accès aux fonctionnalités de Windows disponibles dans les applications Win32, telles que les fichiers mappés en mémoire, la mise en réseau et les graphiques.  Les applications telles que VI, LS et GREP sont les principales cibles du sous\-système POSIX sous Windows.  
  
## Voir aussi  
 [Portage de programmes](http://msdn.microsoft.com/fr-fr/c36c44b3-5a9b-4bb4-9b7a-469aa770ed00)   
 [UNIX](../c-runtime-library/unix.md)   
 [Règles d'inférence](../build/inference-rules.md)