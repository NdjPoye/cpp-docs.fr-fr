---
title: Erreur RC2144 du compilateur de ressources | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC2144
dev_langs: C++
helpviewer_keywords: RC2144
ms.assetid: 1b3ff39a-92cd-4a04-b1a3-b1fa6a805813
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c29a1c1f392372b8dfddd84fa9693010e6a52bfa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rc2144"></a>Erreur RC2144 du compilateur de ressources 
L'ID DE LANGUE PRINCIPALE n'est pas un numéro  
  
 L'ID DE LANGUE PRINCIPALE doit être un ID de langue hexadécimal. Consultez [chaînes de langues et pays/région](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) dans les *Run-Time Library Reference* pour obtenir la liste des ID de langue valide.  
  
 Cette erreur peut aussi se produire si des ressources ont été ajoutées et supprimées à partir du fichier .RC à l'aide d'un outil. Pour résoudre ce problème, ouvrez le fichier .RC dans un éditeur de texte et nettoyez manuellement les ressources non utilisées.