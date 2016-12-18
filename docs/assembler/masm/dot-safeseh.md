---
title: ".SAFESEH | Microsoft Docs"
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
  - ".SAFESEH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "registering functions as exception handlers"
  - "SAFESEH directive"
  - ".SAFESEH directive"
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .SAFESEH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

enregistre une fonction en tant que gestionnaire d'exceptions structuré.  
  
## Syntaxe  
  
```  
  
.SAFESEH identifier  
```  
  
## Notes  
 *l'identificateur* doit être l'ID de [COMMENT](../../assembler/masm/proc.md) ou une COMMENT d' [EXTRN](../../assembler/masm/extrn.md) défini localement.  Vous ne pouvez pas [NOM](../../assembler/masm/label-masm.md) .  la directive de .SAFESEH requiert l'option de ligne de commande de [\/safeseh](../../assembler/masm/ml-and-ml64-command-line-reference.md) ml.exe.  
  
 Pour plus d'informations sur les gestionnaires d'exceptions structurés, consultez [\/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md).  
  
 Par exemple, pour enregistrer un gestionnaire d'exceptions sécurisé, créez un fichier de MASM \(comme suit\), réunissez avec \/safeseh, et l'ajouter aux objets liés.  
  
```  
.386  
.model  flat  
MyHandler   proto  
.safeseh    MyHandler  
end  
```  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)