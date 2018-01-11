---
title: Erreur du compilateur C2441 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2441
dev_langs: C++
helpviewer_keywords: C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 645e06a0685f00359d468a4a4b9bd3522921b511
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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