---
title: "Utilisation d’opérateurs d’extraction | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- extraction operators [C++]
- '&gt;&gt; operator [C++], extraction operators'
- operators [C++], extraction
ms.assetid: a961e1a9-4897-41de-b210-89d5b2d051ae
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 13019040c2deed5c9dd3549d7ab6207553a52bb8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="using-extraction-operators"></a>Utilisation d'opérateurs d'extraction
L’opérateur d’extraction (`>>`), préprogrammé pour tous les types de données C++ standard, représente le moyen le plus simple pour obtenir des octets à partir d’un objet de flux d’entrée.  
  
 Les opérateurs d’extraction d’entrée de texte mis en forme dépendent de l’espace blanc pour séparer les valeurs des données entrantes. Cela n’est pas pratique lorsqu’un champ de texte contient plusieurs mots ou lorsque des virgules séparent les nombres. Dans ce cas, une solution consiste à utiliser la fonction membre d’entrée sans mise en forme [istream::getline](../standard-library/basic-istream-class.md#getline) pour lire un bloc de texte incluant des espaces blancs, puis analyser le bloc avec des fonctions spéciales. Une autre méthode consiste à dériver une classe de flux d’entrée avec une fonction membre telle que `GetNextToken`, qui peut appeler des membres istream pour extraire et mettre en forme les données caractères.  
  
## <a name="see-also"></a>Voir aussi  
 [Flux d’entrée](../standard-library/input-streams.md)

