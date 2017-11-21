---
title: Avertissement du compilateur C4394 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4394
dev_langs: C++
helpviewer_keywords: C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5b201b95a2ec9d43c904de35ca581efbf31b7526
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-c4394"></a>Avertissement du compilateur C4394
'fonction' : symbole par appdomain ne doit pas être marqué avec __declspec (dllexport)  
  
 Une fonction marquée avec la [appdomain](../../cpp/appdomain.md) `__declspec` modificateur est compilé en code MSIL (non natif) et les tables d’exportation ([exporter](../../windows/export.md) `__declspec` modificateur) ne sont pas pris en charge pour les fonctions managées.  
  
 Vous pouvez déclarer une fonction managée d’avoir une accessibilité publique. Pour plus d’informations, consultez [visibilité de Type](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) et [visibilité des membres](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility).  
  
 C4394 est toujours émis en tant qu’erreur.  Vous pouvez désactiver cet avertissement avec le `#pragma warning` ou **/wd**; consultez [avertissement](../../preprocessor/warning.md) ou [Wn, / W0, /W1, /W2, /W3, / W4, /w1, /w2, /w3, / W4, Wall, /wd, / nous, /wo, /WV., /Won (niveau d’avertissement)](../../build/reference/compiler-option-warning-level.md)pour plus d’informations.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C4394.  
  
```  
// C4394.cpp  
// compile with: /clr /c  
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394  
__declspec(dllexport) int g2 = 0;   // OK  
```