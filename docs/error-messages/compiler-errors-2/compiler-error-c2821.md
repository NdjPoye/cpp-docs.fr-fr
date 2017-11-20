---
title: Erreur du compilateur C2821 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2821
dev_langs: C++
helpviewer_keywords: C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f0218061b8d34eca00baa5834053d90711798bd0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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