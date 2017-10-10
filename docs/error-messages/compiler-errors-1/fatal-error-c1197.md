---
title: "Erreur irrécupérable C1197 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1197
dev_langs:
- C++
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d0eb3ab152e9299d47210a6d2c1eb58e3f92a925
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1197"></a>Erreur irrécupérable C1197
Impossible de référencer 'mscorlib.dll_1 ', car le programme a déjà référencé 'mscorlib.dll_2'  
  
 Le compilateur est mis en correspondance avec une version du common language runtime.  Toutefois, une tentative a été effectuée pour faire référence à une version d’un fichier du common language runtime à partir d’une version précédente.  
  
 Pour résoudre cette erreur, seuls les fichiers de référence de la version du common language runtime fourni avec la version de Visual C++, vous compilez avec.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C1197 :  
  
```  
// C1197.cpp  
// compile with: /clr /c  
// processor: x86  
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197  
// try the following line instead  
// #using "mscorlib.dll"  
```
