---
title: Erreur du compilateur C2734 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2734
dev_langs: C++
helpviewer_keywords: C2734
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 73767f86fa4a91b397d31d08a7bf5291502839b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2734"></a>Erreur du compilateur C2734
'identificateur' : un objet const doit être initialisé si pas extern  
  
 L’identificateur est déclaré `const` mais non initialisé ou `extern`.  
  
 L’exemple suivant génère l’erreur C2734 :  
  
```  
// C2734.cpp  
const int j;   // C2734  
extern const int i;   // OK, declared as extern  
```