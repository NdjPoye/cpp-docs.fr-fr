---
title: "Erreur du compilateur C3859 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3859"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3859"
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3859
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

plage de mémoire virtuelle dépassée pour PCH ; recompilez avec une option de ligne de commande '\-Zmvalue' ou supérieur  
  
 Votre en\-tête précompilé est trop petit pour la quantité de données que le compilateur tente d'y placer.  Utilisez l'indicateur de compilateur **\/Zm** pour spécifier une valeur supérieure pour le fichier d'en\-tête précompilé.  Pour plus d'informations, consultez [\/Zm \(Spécifier la limite d'allocation mémoire d'en\-tête précompilé\)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).