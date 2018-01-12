---
title: Erreur du compilateur C2435 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2435
dev_langs: C++
helpviewer_keywords: C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1616208a5ea0b8c3680e87a23846fc58be816623
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2435"></a>Erreur du compilateur C2435
'var' : l’initialisation dynamique requiert un CRT managé, Impossible de compiler avec/clr : safe  
  
 Les options de compilateur **/clr:pure** et **/clr:safe** sont dépréciées dans Visual Studio 2015.  
  
 L’initialisation de variable globale de domaine par application exige la compilation du CRT avec `/clr:pure`, qui ne produit pas d’image vérifiable.  
  
 Pour plus d’informations, consultez [appdomain](../../cpp/appdomain.md) et [process](../../cpp/process.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2435 :  
  
```  
// C2435.cpp  
// compile with: /clr:safe /c  
int globalvar = 0;   // C2435  
  
__declspec(process)  
int globalvar2 = 0;  
```