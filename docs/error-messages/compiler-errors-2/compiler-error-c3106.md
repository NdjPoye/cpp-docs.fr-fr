---
title: "Erreur du compilateur C3106 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3106"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3106"
ms.assetid: 39d97a32-0905-4702-87d3-7f8ce473fb93
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C3106
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribut' : les arguments sans nom doivent précéder les arguments nommés  
  
 Les arguments sans nom doivent être passés à un attribut avant les arguments nommés.  
  
 Pour plus d'informations, consultez [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3106 :  
  
```  
// C3106.cpp  
// compile with: /c  
[module(name="MyLib", dll)];   // C3106  
[module(dll, name="MyLib")];   // OK  
```