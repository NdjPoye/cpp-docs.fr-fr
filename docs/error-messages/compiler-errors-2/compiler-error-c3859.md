---
title: Erreur du compilateur C3859 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3859
dev_langs: C++
helpviewer_keywords: C3859
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d3a240771c0b2e104ef7c51b187d4040500edaae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3859"></a>Erreur du compilateur C3859
plage de mémoire virtuelle dépassée pour PCH ; recompilez avec une option de ligne de commande ’-Zmvalue’ ou supérieur  
  
 Votre en-tête précompilé est trop petit pour la quantité de données que le compilateur tente d’y placer. Utilisez le **/Zm** indicateur de compilateur pour spécifier une valeur supérieure pour le fichier d’en-tête précompilé. Pour plus d’informations, consultez [/Zm (spécifier précompilés en-tête limite d’Allocation mémoire)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).