---
title: Erreur du compilateur C3749 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3749
dev_langs: C++
helpviewer_keywords: C3749
ms.assetid: 3d26b468-4757-41b8-b5a2-78022a5295fb
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 49c231ed1337b683e501dd145055775867f6e2fc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3749"></a>Erreur du compilateur C3749
'attribute' : un attribut personnalisé ne peut pas être utilisé dans une fonction  
  
 Un attribut personnalisé ne peut pas être utilisé dans une fonction. Pour plus d’informations sur les attributs personnalisés, consultez la rubrique [attribut](../../windows/attribute.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3749 :  
  
```  
// C3749a.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::All)]  
public ref struct ABC : public Attribute {  
   ABC() {}  
};  
  
void f1() { [ABC]; };  // C3749  
```  
