---
title: "/SUBSYSTEM | Microsoft Docs"
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
  - "/subsystem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SUBSYSTEM (option Editbin)"
  - "SUBSYSTEM (option Editbin)"
  - "-SUBSYSTEM (option Editbin)"
ms.assetid: 515e4cdf-3cc4-4659-8764-1f2757b49215
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /SUBSYSTEM
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie l'environnement d'exécution requis par l'image exécutable.  
  
```  
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|  
        EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|  
        NATIVE|POSIX|WINDOWS|WINDOWSCE}[,major[.minor]]  
```  
  
## Notes  
 Cette option modifie l'image de façon à indiquer le sous\-système que le système d'exploitation doit appeler pour l'exécution.  
  
 Vous pouvez spécifier l'un des sous\-systèmes suivants :  
  
 BOOT\_APPLICATION  
 Application qui s'exécute dans l'environnement de démarrage de Windows.  Pour plus d'informations sur les applications de démarrage, consultez [À propos du fournisseur WMI BCD](http://msdn.microsoft.com/library/aa362639.aspx).  
  
 CONSOLE  
 Application en mode caractères de Windows.  Le système d'exploitation fournit une console pour les applications console.  
  
 Image EFI \(Extensible Firmware Interface\)  
 Les options du sous\-système EFI \(Extensible Firmware Interface\) décrivent les images exécutables qui s'exécutent dans l'environnement EFI.  Cet environnement est généralement fourni avec le matériel et s'exécute avant que le système d'exploitation soit chargé.  Les principales différences entre les types d'image EFI correspondent à l'emplacement de mémoire dans lequel l'image est chargée et l'action entreprise quand l'appel de l'image est retourné.  Une image EFI\_APPLICATION est déchargée quand le contrôle est retourné.  Un EFI\_BOOT\_SERVICE\_DRIVER ou un EFI\_RUNTIME\_DRIVER est déchargé uniquement si le contrôle est retourné avec un code d'erreur.  Une image EFI\_ROM est exécutée à partir de la mémoire ROM.  Pour plus d'informations, consultez les spécifications sur le site web [Forum EFI unifié](http://www.uefi.org/).  
  
 NATIVE  
 Code qui s'exécute sans environnement de sous\-système. Par exemple, des pilotes de périphérique en mode noyau et des processus système natifs.  Cette option est généralement réservée aux fonctionnalités système de Windows.  
  
 POSIX  
 Application qui s'exécute dans le sous\-système POSIX, dans Windows.  
  
 WINDOWS  
 Application qui s'exécute dans l'environnement graphique de Windows.  Cela inclut les applications de bureau et les applications du Windows Store.  
  
 WINDOWSCE  
 Le sous\-système WINDOWSCE indique que l'application est destinée à s'exécuter sur un périphérique doté d'une version du noyau Windows CE.  Les versions du noyau incluent PocketPC, Windows Mobile, Windows Phone 7, Windows CE V1.0\-6.0R3 et Windows Embedded Compact 7.  
  
 Les valeurs facultatives `major` et `minor` spécifient la version minimale requise du sous\-système spécifié :  
  
-   La partie nombre entier du numéro de version, le segment à gauche du point décimal, est représentée par `major`.  
  
-   La partie fractionnelle du numéro de version \(la partie à droite du point décimal\) est représentée par `minor`.  
  
-   Les valeurs de `major` et `minor` doivent être comprises entre 0 et 65 535.  
  
 Le choix du sous\-système affecte l'adresse de départ par défaut du programme.  Pour plus d'informations, consultez [\/ENTRY \(Symbole de point d'entrée\)](../../build/reference/entry-entry-point-symbol.md), l'option \/ENTRY:*fonction* de l'éditeur de liens.  
  
 Pour plus d'informations, notamment sur les valeurs minimales et par défaut des numéros de version majeure et mineure pour chaque sous\-système, consultez l'option [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) de l'éditeur de liens.  
  
## Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)