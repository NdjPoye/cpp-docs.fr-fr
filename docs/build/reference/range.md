---
title: "/RANGE | Microsoft Docs"
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
  - "/RANGE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RANGE (option Dumpbin)"
  - "-RANGE (option Dumpbin)"
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /RANGE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Modifie la sortie de dumpbin en cas d'utilisation avec d'autres options de dumpbin, telles que \/RAWDATA ou \/DISASM.  
  
## Syntaxe  
  
```  
/RANGE:vaMin[,vaMax]  
```  
  
## Indicateurs  
 **vaMin**  
 Adresse virtuelle à laquelle vous souhaitez que l'opération de dumpbin commence.  
  
 **vaMax** \(facultatif\)  
 Adresse virtuelle à laquelle vous souhaitez que l'opération de dumpbin se termine.  Si elle n'est pas spécifiée, dumpbin continue jusqu'à la fin du fichier.  
  
## Notes  
 Pour afficher les adresses virtuelles d'une image, utilisez le fichier de mappage de l'image \(RVA \+ Base\), l'option **\/DISASM** ou **\/HEADERS** de dumpbin, ou encore la fenêtre Code machine du débogueur Visual Studio.  
  
## Exemple  
 Dans cet exemple, **\/range** permet de modifier l'affichage de l'option **\/disasm**.  La valeur de début est exprimée sous la forme d'un nombre décimal et la valeur de fin est spécifiée sous la forme d'un nombre hexadécimal.  
  
```  
dumpbin /disasm /range:4219334,0x004061CD t.exe  
```  
  
## Voir aussi  
 [Options DUMPBIN](../../build/reference/dumpbin-options.md)