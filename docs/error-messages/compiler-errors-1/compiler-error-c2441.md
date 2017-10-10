---
title: Erreur du compilateur C2441 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2441
dev_langs:
- C++
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6868feadda4c0c0f3d65a86c77a403b8965fded5
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2441"></a>Erreur du compilateur C2441
'variable' : un symbole déclaré avec __declspec (Process) doit être const en/clr : pure en mode  
  
 Les options de compilateur **/clr:pure** et **/clr:safe** sont dépréciées dans Visual Studio 2015.  
  
 Par défaut, les variables sont par domaine d’application sous **/CLR : pure**. Une variable marquée `__declspec(process)` sous **/CLR : pure** est sujette aux erreurs si elle est modifiée dans un domaine d’application et lue dans un autre.  
  
 Par conséquent, le compilateur applique variables par processus `const` sous **/CLR : pure**, rendre les lire uniquement dans tous les domaines d’application.  
  
 Pour plus d’informations, consultez [processus](../../cpp/process.md) et [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C2441.  
  
```  
// C2441.cpp  
// compile with: /clr:pure /c  
__declspec(process) int i;   // C2441  
__declspec(process) const int j = 0;   // OK  
```
