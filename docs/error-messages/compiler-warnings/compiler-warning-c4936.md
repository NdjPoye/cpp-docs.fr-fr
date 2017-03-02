---
title: "C4936 d’avertissement du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4936
dev_langs:
- C++
helpviewer_keywords:
- C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 58d702067c186eeeea94768a03836b64577961ca
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-c4936"></a>Avertissement du compilateur C4936
ce __declspec est pris en charge uniquement lorsqu'il est compilé avec /clr ou /clr:pure  
  
 Le **/CLR : pure** option du compilateur est déconseillée dans Visual Studio 2015.  
  
 A `__declspec` modificateur a été utilisé mais qui `__declspec` modificateur est uniquement valide lors de la compilation avec un de le [/clr](../../build/reference/clr-common-language-runtime-compilation.md) options.  
  
 Pour plus d’informations, consultez [appdomain](../../cpp/appdomain.md) et [processus](../../cpp/process.md).  
  
 C4936 est toujours émis en tant qu’erreur.  Vous pouvez désactiver C4936 avec la [avertissement](../../preprocessor/warning.md) pragma.  
  
 L’exemple suivant génère l’avertissement C4936 :  
  
```  
// C4936.cpp  
// compile with: /c  
// #pragma warning (disable : 4936)  
__declspec(process) int i;   // C4936  
__declspec(appdomain) int j;   // C4936  
```
