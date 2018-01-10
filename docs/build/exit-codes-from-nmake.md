---
title: Codes de sortie de NMAKE | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 13cbe4806d8b3960cbf80df41c7cce6e7657ba7e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="exit-codes-from-nmake"></a>Codes de sortie de NMAKE
NMAKE retourne les codes de sortie suivants :  
  
|Code|Signification|  
|----------|-------------|  
|0|Aucune erreur (probablement un avertissement)|  
|1|Génération incomplète (émise seulement quand l’option /K est utilisée)|  
|2|Erreur de programme, probablement en raison d’une des valeurs suivantes :|  
||-Une erreur de syntaxe dans le makefile|  
||-Un erreur ou code de sortie à partir d’une commande|  
||-Une interruption par l’utilisateur|  
|4|Erreur système : mémoire insuffisante|  
|255|Cible n’est pas à jour (émis seulement quand l’option /Q est utilisée)|  
  
## <a name="see-also"></a>Voir aussi  
 [Exécution de NMAKE](../build/running-nmake.md)