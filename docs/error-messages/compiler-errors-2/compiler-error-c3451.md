---
title: Erreur du compilateur C3451 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3451
dev_langs: C++
helpviewer_keywords: C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cb68c546a9064801c68844039b7de077d5ee7c17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3451"></a>Erreur du compilateur C3451
'attribut' : Impossible d’appliquer l’attribut non managé à 'type'  
  
 Un attribut C++ ne peut pas être appliqué à un type CLR. Consultez [référence des attributs C++](../../windows/cpp-attributes-reference.md) pour plus d’informations.  
  
 Pour plus d'informations, consultez [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
 Cette erreur peut être due à la mise en conformité du compilateur pour Visual C++ 2005 : la [uuid](../../windows/uuid-cpp-attributes.md) attribut n’est plus autorisé sur un attribut défini par l’utilisateur à l’aide de la programmation CLR. Utilisez plutôt <xref:System.Runtime.InteropServices.GuidAttribute>.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C3451.  
  
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