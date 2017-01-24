---
title: "Erreur du compilateur C3235 | Microsoft Docs"
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
  - "C3235"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3235"
ms.assetid: 0554d6c7-e1dc-4c99-8934-cbcf491c8203
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3235
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'specialization' : la spécialisation explicite ou partielle d’une classe générique n’est pas autorisée  
  
 Les classes génériques ne peuvent pas être utilisées pour les spécialisations explicites ou partielles.  
  
## Exemple  
 L’exemple suivant génère l’erreur C3235.  
  
```  
// C3235.cpp // compile with: /clr generic<class T> public ref class C {}; generic<> public ref class C<int> {};   // C3235 Remove this specialization to resolve this error.  
```