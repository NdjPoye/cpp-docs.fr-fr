---
title: "Erreur irrécupérable NMAKE U1100 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1100
dev_langs: C++
helpviewer_keywords: U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e7c4a42e47a29775bb53fdc0fd2f25c7bdc252f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1100"></a>Erreur irrécupérable NMAKE U1100
la macro 'nom_macro' non conforme dans le contexte de la rŠgle batch 'rule'  
  
 NMAKE génère cette erreur lorsque le bloc de commande d’une règle en mode batch directement ou indirectement référence à une macro de fichier spécial qui n’est pas $<.  
  
 $< est le seul autorisé (macro) pour les règles en mode batch.