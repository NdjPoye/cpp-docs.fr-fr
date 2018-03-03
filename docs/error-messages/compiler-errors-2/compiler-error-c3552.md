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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ca49c6678a147988ee0b2fb0ab57b6883b80539a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3552"></a>Erreur du compilateur C3552
'typename' : un type de retour spécifié à la fin ne peut pas contenir 'auto'  
  
 Si vous utilisez le mot clé `auto` en tant qu’espace réservé pour le type de retour d’une fonction, vous devez fournir un type de retour spécifié à la fin. Toutefois, vous ne pouvez pas utiliser un autre mot clé `auto` pour spécifier le type de retour spécifié à la fin. Par exemple, le fragment de code suivant génère l’erreur C3552.  
  
 `auto myFunction->auto; // C3552`