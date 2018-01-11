---
title: 3.3 Routines de minutage | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 21060d64-cbe8-4e38-8718-3a68d6a57be3
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 05f9e7c8eedbf1803e1bfbc3c744c5d8b9c9fd99
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="33-timing-routines"></a>3.3 Routines de minutage
Les fonctions décrites dans cette section prennent en charge un minuteur d’horloge portables :  
  
-   Le `omp_get_wtime` fonction retourne le temps horloge écoulé.  
  
-   Le `omp_get_wtick` fonction retourne les secondes entre les battements d’horloge successives.