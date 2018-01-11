---
title: Compilateur avertissement (niveau 1) C4794 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4794
dev_langs: C++
helpviewer_keywords: C4794
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5c6878e2e0fb3fed9cb349bd0dd651a24c02aae9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4794"></a>Avertissement du compilateur (niveau 1) C4794
segment de variable de thread de stockage local 'variable' modifié de 'section name' en '.tls$'  
  
 Vous avez utilisé [#pragma data_seg](../../preprocessor/data-seg.md) pour placer une variable tls dans une section qui ne commence pas par .tls$.  
  
 La section .tls$*x* existe dans le fichier objet dans lequel sont définies des variables [__declspec(thread)](../../cpp/thread.md) . Une section .tls dans le fichier EXE ou DLL résulte de ces sections.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’avertissement C4794 :  
  
```  
// C4794.cpp  
// compile with: /W1 /c  
#pragma data_seg(".someseg")  
__declspec(thread) int i;   // C4794  
  
// OK  
#pragma data_seg(".tls$9")  
__declspec(thread) int j;  
```