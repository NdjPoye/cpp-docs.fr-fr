---
title: "Erreur du compilateur C3373 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3373"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3373"
ms.assetid: 6e7586c3-1a15-4773-ad20-f90090a400dc
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Erreur du compilateur C3373
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l’attribut 'attribute' n’accepte aucun argument sauf sur une coclasse  
  
 Certains attributs peuvent être appliqués à plusieurs constructions C\+\+, mais les arguments de l’attribut peuvent uniquement être autorisés sur certaines constructions.  
  
 L’exemple suivant génère l’erreur C3373 :  
  
```  
// C3373.cpp #include <windows.h> [module(name="MyModule")]; [ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ] __interface IMyIface { // arguments to source and restricted are not allowed when // these attributes are applied to an interface [source(IMyIface)] HRESULT f1(); [restricted(IMyIface)] HRESULT f2(); // C3373 }; [ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f) ] class CMyClass : public IMyIface { }; int main() { }  
```