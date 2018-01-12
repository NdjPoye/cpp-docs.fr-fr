---
title: Erreur du compilateur C2307 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2307
dev_langs: C++
helpviewer_keywords: C2307
ms.assetid: ce6c8033-a673-4679-9883-bedec36ae385
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7a918885d9523e1e068e73bcd0e4b8f712f3b5ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2307"></a>Erreur du compilateur C2307
pragma 'pragma' doit être une fonction externe si la compilation incrémentielle est activée  
  
 Vous devez placer le `data_seg` pragma entre les fonctions si vous utilisez la compilation incrémentielle.