---
title: Erreur du compilateur C2821 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2821
dev_langs:
- C++
helpviewer_keywords:
- C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 774c191bb3da3c5382c4aff7d48c8d6ae5ca7e68
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="compiler-error-c2821"></a>Erreur du compilateur C2821
premier paramètre formel de 'operator new' doit être 'unsigned int'  
  
Le premier paramètre formel de la [new, opérateur](../../standard-library/new-operators.md#op_new) doit être non `int`.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2821 :  
  
```cpp  
// C2821.cpp  
// compile with: /c  
void * operator new( /* unsigned int,*/ void * );   // C2821  
void * operator new( unsigned int, void * );  
```
