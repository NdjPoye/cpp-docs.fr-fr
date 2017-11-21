---
title: Erreur du compilateur C3113 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3113
dev_langs: C++
helpviewer_keywords: C3113
ms.assetid: 3afdc668-b29e-474e-9ea3-aa027d42db7c
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 53d13466368ce1b9e473c2c2fce1c96f3d9a0f81
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3113"></a>Erreur du compilateur C3113
une 'structure' ne peut pas être un modèle/générique  
  
 Vous avez tenté de rendre un modèle de classe ou une classe générique hors d’une interface ou une énumération.  
  
 L’exemple suivant génère l’erreur C3113 :  
  
```  
// C3113.cpp  
// compile with: /c  
template <class T>   
enum E {};   // C3113  
// try the following line instead  
// class MyClass{};  
```