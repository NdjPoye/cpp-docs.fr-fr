---
title: Erreur du compilateur C3900 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3900
dev_langs:
- C++
helpviewer_keywords:
- C3900
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e7d85041e90584822397302c39a1050fb59b2b34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3900"></a>Erreur du compilateur C3900
'membre' : non autorisé dans la portée actuelle  
  
 Blocs de propriété peuvent contenir les déclarations de fonction et des définitions de fonction inline. Aucuns autres fonctions membres ne sont autorisés dans les blocs de propriété. Aucune fonction friend, opérateurs ou typedefs n’est autorisées. Pour plus d'informations, consultez [property](../../windows/property-cpp-component-extensions.md).  
  
 Les définitions d’événements ne peuvent contenir que des méthodes d’accès et des fonctions.  
  
 L’exemple suivant génère C3900 :  
  
```  
// C3900.cpp  
// compile with: /clr  
ref class X {  
   property int P {  
      void set(int);   // OK  
      int i;   // C3900 variable declaration  
   };  
};  
```  
  
 L’exemple suivant génère C3900 :  
  
```  
// C3900b.cpp  
// compile with: /clr  
using namespace System;  
delegate void H();  
ref class X {  
   event H^ E {  
      int m;   // C3900  
  
      // OK  
      void Test() {}  
  
      void add( H^ h ) {}  
      void remove( H^ h ) {}  
      void raise( ) {}  
   }  
};  
```