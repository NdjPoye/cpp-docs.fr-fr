---
title: "Erreur du compilateur C3451 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3451"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3451"
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3451
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribut' : impossible d'appliquer l'attribut non managé à 'type'  
  
 Un attribut C\+\+ ne peut pas être appliqué à un type CLR.  Pour plus d'informations, consultez [C\+\+ Attributes Reference](../../windows/cpp-attributes-reference.md).  
  
 Pour plus d'informations, consultez [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
 Cette erreur peut être due à la mise en conformité du compilateur pour Visual C\+\+ 2005 : l'attribut [uuid](../../windows/uuid-cpp-attributes.md) n'est plus autorisé sur un attribut défini par l'utilisateur à l'aide de la programmation CLR.  Utilisez plutôt <xref:System.Runtime.InteropServices.GuidAttribute>.  
  
## Exemple  
 L'exemple suivant génère l'erreur C3451 :  
  
```  
// C3451.cpp  
// compile with: /clr /c  
using namespace System;  
[ attribute(AttributeTargets::All) ]  
public ref struct MyAttr {};  
  
[ MyAttr, helpstring("test") ]   // C3451  
// try the following line instead  
// [ MyAttr ]  
public ref struct ABC {};  
```