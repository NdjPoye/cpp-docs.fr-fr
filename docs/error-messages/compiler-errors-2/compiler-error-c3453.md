---
title: "Erreur du compilateur C3453 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3453"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3453"
ms.assetid: dbefdbcf-f697-4239-b7a5-1d99b85e9e7f
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3453
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribut' : attribut non appliqué, car le qualificateur 'assembly' ne correspond pas  
  
 Les attributs de niveau assembly ou module peuvent uniquement être spécifiés comme des instructions autonomes.  
  
## Exemple  
 L’exemple suivant génère l’erreur C3453 :  
  
```  
// C3453.cpp // compile with: /clr /c [assembly:System::CLSCompliant(true)]   // C3453 // try the following line instead // [assembly:System::CLSCompliant(true)]; ref class X {};  
```