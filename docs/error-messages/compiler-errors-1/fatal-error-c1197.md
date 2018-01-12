---
title: "Erreur irrécupérable C1197 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1197
dev_langs: C++
helpviewer_keywords: C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1658e55a9298df703051b856bb9b10dd02d8cc68
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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