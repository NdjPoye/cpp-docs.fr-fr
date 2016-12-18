---
title: "/APPCONTAINER | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/APPCONTAINER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/APPCONTAINER (option editbin)"
  - "APPCONTAINER (option editbin)"
  - "-APPCONTAINER (option editbin)"
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /APPCONTAINER
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Marque un fichier exécutable qui doit s’exécuter dans un conteneur d’application, par exemple une [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] ou une application Windows universelle.  
  
```  
  
/APPCONTAINER[:NO]  
```  
  
## Notes  
 Un fichier exécutable dont l’option **\/APPCONTAINER** est définie ne peut être exécuté que dans un conteneur d’application, ce qui correspond à l’environnement d’isolation des processus introduit dans Windows 8. Pour [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] et les applications Windows universelles, cette option doit être définie.  
  
## Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)   
 [Qu’est\-ce qu’une application Windows universelle ?](http://go.microsoft.com/fwlink/p/?LinkID=522074)