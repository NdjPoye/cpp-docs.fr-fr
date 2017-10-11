---
title: Erreur du compilateur C3552 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3552
dev_langs:
- C++
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 54526c39a928cc534ba815ef8fda802db85f4020
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3552"></a>Erreur du compilateur C3552
'typename' : un type de retour spécifié à la fin ne peut pas contenir 'auto'  
  
 Si vous utilisez le mot clé `auto` en tant qu’espace réservé pour le type de retour d’une fonction, vous devez fournir un type de retour spécifié à la fin. Toutefois, vous ne pouvez pas utiliser un autre mot clé `auto` pour spécifier le type de retour spécifié à la fin. Par exemple, le fragment de code suivant génère l’erreur C3552.  
  
 `auto myFunction->auto; // C3552`
