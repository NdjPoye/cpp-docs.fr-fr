---
title: Erreur du compilateur C2947 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2947
dev_langs:
- C++
helpviewer_keywords:
- C2947
ms.assetid: 6c056f62-ec90-4883-8a67-aeeb6ec13546
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1af4e6a5a27c13d69351eaf0cddfafe11ba5f22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2947"></a>Erreur du compilateur C2947
attendu ' >' pour mettre fin à la construction, 'syntaxe' trouvé  
  
 Une liste d’arguments génériques ou de modèle n’a ne peut-être pas été fermée correctement.  
  
 L’erreur C2947 peut également être générée par des erreurs de syntaxe.  
  
 L’exemple suivant génère l’erreur C2947 :  
  
```  
// C2947.cpp  
// compile with: /c  
template <typename T>=   // C2947  
// try the following line instead  
// template <typename T>  
struct A {};  
```