---
title: Compilateur avertissement (niveau 4) C4266 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4266
dev_langs: C++
helpviewer_keywords: C4266
ms.assetid: 90ec5f5b-3451-4c16-bb1b-c30a626bdaa0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 88cd587c142243b1a97ee6afd59cbc519b36180a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4266"></a>Avertissement du compilateur (niveau 4) C4266
'fonction' : aucune substitution disponible pour la fonction membre virtuelle de base 'type' ; la fonction est masquée  
  
 Une classe dérivée n’a substitué toutes les surcharges de fonction virtuelle.  
  
 Cet avertissement est désactivé par défaut.  Consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md) pour plus d'informations.  
  
 L’exemple suivant génère l’erreur C4266 :  
  
```  
// C4266.cpp  
// compile with: /W4 /c  
#pragma warning (default : 4266)  
class Engine {  
public:  
   virtual void OnException(int&,int);  
   virtual void OnException(int&,int&,int);  
};  
  
class LocalBinding : private Engine {  
   virtual void OnException(int&,int);  
};   // C4266  
```  
  
 Résolution possible :  
  
```  
// C4266b.cpp  
// compile with: /W4 /c  
#pragma warning (default : 4266)  
class Engine {  
public:  
   virtual void OnException(int&,int);  
   virtual void OnException(int&,int&,int);  
};  
  
class LocalBinding : private Engine {  
   virtual void OnException(int&,int);  
   virtual void OnException(int&, int&, int);  
};  
```