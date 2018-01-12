---
title: "Erreur irrécupérable C1091 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1091
dev_langs: C++
helpviewer_keywords: C1091
ms.assetid: 812d4201-9154-48b0-b9af-5959c082ca33
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9e9d5e9ba75457d89223ab187c1249cc73419fab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1091"></a>Erreur irrécupérable C1091
Limite du compilateur : la longueur de la chaîne dépasse de 'longueur' octets  
  
 Une constante de chaîne a dépassé la limite actuelle de longueur de chaîne.  
  
 Fractionnez la chaîne statique en deux variables (ou davantage) et utilisez [strcpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) pour joindre le résultat dans le cadre de la déclaration ou au moment de l’exécution.