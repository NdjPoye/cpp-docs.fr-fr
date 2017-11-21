---
title: Erreur du compilateur C2149 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2149
dev_langs: C++
helpviewer_keywords: C2149
ms.assetid: 7a106dab-d79f-41b9-85be-f36e86e4d2ab
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3e181d4fc2d5ee10533d2a0e13142e827863d762
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2149"></a>Erreur du compilateur C2149
'identificateur' : un champ de bits nommé ne peut pas avoir une largeur égale à zéro  
  
 Les champs de bits ne peuvent avoir une largeur égale à zéro que s’ils ne portent pas de nom.  
  
 L’exemple suivant génère l’erreur C2149 :  
  
```  
// C2149.cpp  
// compile with: /c  
struct C {  
   int i : 0;   // C2149  
   int j : 2;   // OK  
};  
```