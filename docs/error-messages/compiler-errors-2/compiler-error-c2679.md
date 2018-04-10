---
title: Erreur du compilateur C2679 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C2679
dev_langs:
- C++
helpviewer_keywords:
- C2679
ms.assetid: 1a5f9d00-9190-4aa6-bc72-949f68ec136f
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f5c32e92ccdbccbeb2683e44d6d5aaeabc6db8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2679"></a>Erreur du compilateur C2679
'opérateur' binaire : aucun opérateur ne trouvé qui accepte un opérande de droite de type 'type' (ou il n’existe aucune conversion acceptable)  
  
 Pour utiliser l'opérateur, vous devez le surcharger pour le type spécifié ou définir une conversion vers un type pour lequel l'opérateur est défini.  
  
 L’exemple suivant génère l’erreur C2679 :  
  
```  
// C2679.cpp  
class C {  
public:  
   C();   // no constructor with an int argument  
} c;  
  
class D {  
public:  
   D(int) {}  
   D(){}  
} d;  
  
int main() {  
   c = 10;   // C2679  
   d = 10;   // OK  
}  
```