---
title: Erreur du compilateur C2719 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2719
dev_langs: C++
helpviewer_keywords: C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f7e6707dfd5666cb8852e3bbf59cf7a81dd24766
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2719"></a>Erreur du compilateur C2719
'paramètre' : le paramètre formel avec __declspec(align('#')) ne sera pas aligné  
  
 Le [aligner](../../cpp/align-cpp.md) `__declspec` modificateur n’est pas autorisé sur les paramètres de fonction. L’alignement des paramètres de fonction est contrôlé par la convention d’appel utilisée. Pour plus d’informations, consultez [Conventions d’appel](../../cpp/calling-conventions.md).  
  
 L'exemple suivant génère l'erreur C2719 et montre comment la corriger :  
  
```  
// C2719.cpp  
void func(int __declspec(align(32)) i);   // C2719  
// try the following line instead  
// void func(int i);  
```