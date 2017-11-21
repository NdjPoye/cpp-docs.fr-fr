---
title: Compilateur avertissement (niveau 4) C4268 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4268
dev_langs: C++
helpviewer_keywords: C4268
ms.assetid: d0511e80-904f-4ee1-b4d7-39b5c0bd8234
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ef285e3c093dec39c181e92071fd7b16161d4377
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4268"></a>Avertissement du compilateur (niveau 4) C4268
'identificateur' : 'const' données static/global initialisées avec le constructeur de valeur par défaut généré par le compilateur remplissent l’objet de zéros  
  
 A **const** instance globale ou statique d’une classe non triviale est initialisée avec un constructeur par défaut de généré par le compilateur.  
  
## <a name="example"></a>Exemple  
  
```  
// C4268.cpp  
// compile with: /c /LD /W4  
class X {  
public:  
   int m_data;  
};  
  
const X x1;   // C4268  
```  
  
 Cette instance de la classe est **const**, la valeur de `m_data` ne peut pas être modifié.