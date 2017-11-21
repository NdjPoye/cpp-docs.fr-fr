---
title: Erreur du compilateur C3383 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3383
dev_langs: C++
helpviewer_keywords: C3383
ms.assetid: ceb7f725-f417-4dc3-8496-0f413bb76687
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2a97cd1348bc927b633e683bed80a6b907f88a58
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3383"></a>Erreur du compilateur C3383
'operator new' n'est pas pris en charge avec /clr:safe  
  
 Le fichier de sortie d’une compilation **/clr:safe** est un fichier de type sécurisé vérifiable qui ne prend pas en charge les pointeurs.  
  
 Pour plus d'informations, consultez  
  
-   [/CLR (Compilation pour le common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Problèmes courants de migration vers Visual C++ 64 bits](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3383.  
  
```  
// C3383.cpp  
// compile with: /clr:safe  
int main() {  
   char* pCharArray = new char[256];  // C3383  
}  
```