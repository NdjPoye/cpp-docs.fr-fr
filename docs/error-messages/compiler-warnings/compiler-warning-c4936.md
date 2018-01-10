---
title: Avertissement du compilateur C4936 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4936
dev_langs: C++
helpviewer_keywords: C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 995cd7b2b774b768d6bccf10ddcec18101580e74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4936"></a>Avertissement du compilateur C4936
ce __declspec est pris en charge uniquement lorsqu'il est compilé avec /clr ou /clr:pure  
  
 Le **/CLR : pure** option du compilateur est déconseillée dans Visual Studio 2015.  
  
 Un modificateur `__declspec` a été utilisé, mais ce modificateur `__declspec` est valide uniquement quand il est compilé avec l’une des options [/clr](../../build/reference/clr-common-language-runtime-compilation.md) .  
  
 Pour plus d’informations, consultez [appdomain](../../cpp/appdomain.md) et [process](../../cpp/process.md).  
  
 C4936 est toujours émis en tant qu’erreur.  Vous pouvez désactiver C4936 avec le pragma [warning](../../preprocessor/warning.md) .  
  
 L’exemple suivant génère l’avertissement C4936 :  
  
```  
// C4936.cpp  
// compile with: /c  
// #pragma warning (disable : 4936)  
__declspec(process) int i;   // C4936  
__declspec(appdomain) int j;   // C4936  
```