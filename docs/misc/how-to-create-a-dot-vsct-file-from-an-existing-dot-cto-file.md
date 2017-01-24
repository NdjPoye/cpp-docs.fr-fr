---
title: "Comment&#160;: cr&#233;er un fichier .Vsct &#224; partir d’un fichier .Cto existant | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "fichiers VSCT, création basée sur un fichier .cto"
ms.assetid: 847717c9-477d-4ac9-8b2c-2da878912478
caps.latest.revision: 11
caps.handback.revision: 11
manager: "douge"
---
# Comment&#160;: cr&#233;er un fichier .Vsct &#224; partir d’un fichier .Cto existant
Vous pouvez créer un fichier .vsct XML à partir d’un fichier .cto binaire existant. Cela vous permet de tirer parti du nouveau format de compilateur de la table de commande. Ce processus fonctionne même si le fichier .cto a été compilé à partir d’un fichier .ctc. Vous pouvez modifier et compiler le fichier .vsct dans un autre fichier .cto.  
  
### Pour créer un fichier .vsct à partir d’un fichier .cto  
  
1.  Obtenez des copies du fichier .cto et de son fichier .ctsym correspondant.  
  
2.  Placez les fichiers dans le même répertoire que le compilateur vsct.exe.  
  
3.  À l’invite de commandes Visual Studio, accédez au répertoire qui contient les fichiers .cto et .ctsym.  
  
4.  Tapez **vsct.exe** *ctofilename***.cto** *vsctfilename***.vsct \-S***symfilename***.ctsym**.  
  
     `ctofilename` est le nom du fichier .cto, `vsctfilename` est le nom du fichier vsct que vous souhaitez créer et `symfilename` est le nom du fichier .ctsym.  
  
     Ce processus crée un fichier de compilateur de la table de commande XML .vsct. Vous pouvez modifier et compiler le fichier avec vsct.exe, le compilateur vsct, comme vous le feriez pour tout autre fichier .vsct.  
  
## Voir aussi  
 [Comment : créer un. Fichier VSCT](../Topic/How%20to:%20Create%20a%20.Vsct%20File.md)   
 [Table de commandes de Visual Studio \(. Fichiers VSCT\)](../Topic/Visual%20Studio%20Command%20Table%20\(.Vsct\)%20Files.md)