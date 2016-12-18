---
title: "Erreur du compilateur C2262 | Microsoft Docs"
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
  - "C2262"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2262"
ms.assetid: 727d1c6e-53e8-40e5-b7b8-6a7ac2011727
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2262
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'spécificateurs\_attributs' : aucune version, culture ou architecture de processeur ne peut être spécifiée pour les déclarations InternalsVisible  
  
 L’attribut <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> n’a pas été spécifié correctement.  
  
## Exemple  
 L’exemple suivant génère l’erreur C2262 :  
  
```  
// C2262.cpp // compile with: /clr /c using namespace System::Runtime::CompilerServices; [assembly: InternalsVisibleTo("assembly_name, version=1.2.3.7")];   // C2262 [assembly: InternalsVisibleTo("assembly_name ")];   // OK  
```