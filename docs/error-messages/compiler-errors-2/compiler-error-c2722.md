---
title: Erreur du compilateur C2722 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2722
dev_langs:
- C++
helpviewer_keywords:
- C2722
ms.assetid: 4cc2c7fa-cb12-4bcf-9df1-6d627ef62973
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2f8526422129b1fe114974de1c7f95cb55117d99
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2722"></a>Erreur du compilateur C2722
' :: opérateur ' : non conforme après une commande operator ; Utilisez 'operator opérateur'  
  
 Un `operator` instruction redéfinit `::new` ou `::delete`. Le `new` et `delete` opérateurs sont globaux, par conséquent, l’opérateur de résolution de portée (`::`) n’a aucune signification. Supprimer le `::` opérateur.