---
title: "Erreur mathématique M6202 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: M6202
dev_langs: C++
helpviewer_keywords: M6202
ms.assetid: 4d17045f-c6dc-4705-9512-e9af12c35fb4
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 70a9496a2466ee36fed6d9c16194eef3516147f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="math-error-m6202"></a>Erreur mathématique M6202
'fonction' : erreur  
  
 Un argument de la fonction était une valeur de singularité pour cette fonction. La fonction n’est pas définie pour cet argument.  
  
 Cette erreur appelle la `_matherr` fonction avec le type d’erreur, le nom de fonction et ses arguments. Vous pouvez réécrire la `_matherr` afin de personnaliser la gestion de certaines erreurs mathématiques à virgule flottante d’exécution.