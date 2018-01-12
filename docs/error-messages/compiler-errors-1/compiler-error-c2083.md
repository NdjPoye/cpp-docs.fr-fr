---
title: Erreur du compilateur C2083 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2083
dev_langs: C++
helpviewer_keywords: C2083
ms.assetid: 5fc4f931-eab6-4d8d-a3ee-3b8e11e64b18
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 50f269caa36d3111d59295f066f37223254d87aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2083"></a>Erreur du compilateur C2083
comparaison struct/union non conforme  
  
 Une structure ou une union est comparée directement à un autre type défini par l’utilisateur. Cela n’est pas autorisé, sauf si un opérateur de comparaison a été défini ou s’il existe une conversion vers un type scalaire.