---
title: "/DEBUGTYPE (options d&#39;informations de d&#233;bogage) | Microsoft Docs"
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
  - "/debugtype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DEBUGTYPE, option de l'éditeur de liens"
  - "DEBUGTYPE, option de l'éditeur de liens"
  - "-DEBUGTYPE, option de l'éditeur de liens"
ms.assetid: 1ddcb718-7fec-4f92-a319-3f70f04fe742
caps.latest.revision: 2
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DEBUGTYPE (options d&#39;informations de d&#233;bogage)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'option \/DEBUGTYPE spécifie les types d'informations de débogage générées par l'option \/DEBUG.  
  
```  
/DEBUGTYPE:[CV | PDATA | FIXUP]  
```  
  
## Arguments  
 CV  
 Indique à l'éditeur de liens d'émettre des informations de débogage pour les symboles, les numéros de ligne et d'autres informations de compilation d'objet dans le fichier PDB.  Par défaut, cette option est activée quand **\/DEBUG** est spécifié et que **\/DEBUGTYPE** n'est pas spécifié.  
  
 PDATA  
 Indique à l'éditeur de liens d'ajouter des entrées .pdata et .xdata aux informations de flux de débogage dans le fichier PDB.  Par défaut, cette option est activée quand les deux options **\/DEBUG** et **\/DRIVER** sont spécifiées.  Si **\/DEBUGTYPE:PDATA** est spécifié de lui\-même, l'éditeur de liens inclut automatiquement les symboles de débogage dans le fichier PDB.  Si **\/DEBUGTYPE:PDATA,FIXUP** est spécifié, l'éditeur de liens n'inclut pas les symboles de débogage dans le fichier PDB.  
  
 FIXUP  
 Indique à l'éditeur de liens d'ajouter des entrées de table de réadressage aux informations de flux de débogage dans le fichier PDB.  Par défaut, cette option est activée quand les deux options **\/DEBUG** et **\/PROFILE** sont spécifiées.  Si **\/DEBUGTYPE:FIXUP** ou **\/DEBUGTYPE:FIXUP,PDATA** est spécifié, l'éditeur de liens n'inclut pas les symboles de débogage dans le fichier PDB.  
  
 Il est possible de combiner les arguments de **\/DEBUGTYPE** dans un ordre quelconque en les séparant par des virgules.  L'option **\/DEBUGTYPE** et ses arguments ne respectent pas la casse.  
  
## Notes  
 Utilisez l'option **\/DEBUGTYPE** pour spécifier l'inclusion des données de table de réadressage ou des informations d'en\-tête .pdata et .xdata dans le flux de débogage.  Par conséquent, l'éditeur de liens inclut des informations concernant le code en mode utilisateur qui est visible dans un débogueur du noyau lors de la séparation de code en mode noyau.  Pour rendre les symboles de débogage disponibles quand **FIXUP** est spécifié, incluez l'argument **CV**.  
  
 Pour déboguer du code en mode utilisateur, ce qui est habituel pour les applications, l'option **\/DEBUGTYPE** n'est pas nécessaire.  Par défaut, les commutateurs de compilation qui spécifient la sortie de débogage \([\/Z7, \/Zi, \/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)\) émettent toutes les informations requises par le débogueur Visual Studio.  Utilisez **\/DEBUGTYPE:PDATA** ou **\/DEBUGTYPE:CV,PDATA,FIXUP** pour déboguer du code qui combine des composants en mode utilisateur et en mode noyau, tels qu'une application de configuration pour un pilote de périphérique.  Pour plus d'informations sur les débogueurs en mode noyau, consultez [Outils de débogage pour Windows \(WinDbg, KD, CDB, NTSD\)](http://go.microsoft.com/fwlink/p?LinkID=285651)  
  
## Voir aussi  
 [\/DEBUG \(Générer les informations de débogage\)](../../build/reference/debug-generate-debug-info.md)   
 [\/DRIVER \(Pilote Windows NT en mode noyau\)](../../build/reference/driver-windows-nt-kernel-mode-driver.md)   
 [\/PROFILE \(Profileur des outils d'analyse des performances\)](../../build/reference/profile-performance-tools-profiler.md)   
 [Outils de débogage pour Windows \(WinDbg, KD, CDB, NTSD\)](http://go.microsoft.com/fwlink/p?LinkID=285651)