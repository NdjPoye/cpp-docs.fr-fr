---
title: Erreur du compilateur C2449 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2449
dev_langs:
- C++
helpviewer_keywords:
- C2449
ms.assetid: 544bf0b6-daa0-40e8-9f21-8e583d472a2d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a2ea92f79125e4e3b96f35229a487a5ab787e1d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2449"></a>Erreur du compilateur C2449
trouvé ' {' au niveau de la portée du fichier (en-tête de fonction manquant ?)  
  
 Une accolade ouvrante se produit au niveau de la portée du fichier.  
  
 Cette erreur peut être provoquée par un point-virgule entre un en-tête de fonction et l’accolade ouvrante de la définition de fonction.  
  
 L’exemple suivant génère l’erreur C2499 :  
  
```  
// C2449.c  
// compile with: /c  
void __stdcall func(void) {}   // OK  
void __stdcall func(void);  // extra semicolon on this line  
{                         // C2449 detected here  
```