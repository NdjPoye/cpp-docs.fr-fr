---
title: Erreur du compilateur C3675 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3675
dev_langs: C++
helpviewer_keywords: C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d45236fc32fd0d10e9617b6946683d8ebd73ef0e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3675"></a>Erreur du compilateur C3675
'fonction' : est réservé, car 'propriété' est définie.  
  
 Lorsque vous déclarez une propriété simple, le compilateur génère get et méthodes d’accesseur set et ces noms sont présents dans la portée de votre programme.  Les noms générés par le compilateur sont constitués en ajoutant get_ et set_ au nom de propriété.  Par conséquent, vous ne pouvez pas déclarer des fonctions avec le même nom que les accesseurs générés par le compilateur.  
  
 Pour plus d'informations, voir [property](../../windows/property-cpp-component-extensions.md) .  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C3675.  
  
```  
// C3675.cpp  
// compile with: /clr /c  
ref struct C {  
public:  
   property int Size;  
   int get_Size() { return 0; }   // C3675  
};  
```