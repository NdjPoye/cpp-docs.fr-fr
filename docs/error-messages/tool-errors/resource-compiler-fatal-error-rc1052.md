---
title: "Erreur irrécupérable RC1052 du compilateur de ressources | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC1052
dev_langs: C++
helpviewer_keywords: RC1052
ms.assetid: 59803673-492b-44fa-80fa-df93b8aaf9fb
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0546441022d8e2b487d83e291574020665cdaf4c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rc1052"></a>Erreur irrécupérable RC1052 du compilateur de ressources 
limite du compilateur : blocs #if ou #ifdef imbriqués trop profondément  
  
 Le programme a dépassé le nombre maximal de niveaux d'imbrication autorisés pour les directives `#if` et `#ifdef`.  
  
 Cette erreur peut être provoquée par des fichiers include qui utilisent ces directives de préprocesseur.  
  
 Pour résoudre ce problème, réduisez le nombre de directives `#if` et `#ifdef` imbriquées dans votre fichier de ressources. Si le problème est provoqué par les fichiers d'en-tête inclus dans votre fichier de ressources, réduisez le nombre de directives `#if` et `#ifdef` imbriquées dans les fichiers d'en-tête. Si ce n'est pas possible, créez un fichier d'en-tête et incluez-le dans votre fichier de ressources, en exécutant le préprocesseur sur les fichiers d'en-tête inclus existants. Pour plus d’informations, consultez la [/P (Prétraiter dans un fichier)](../../build/reference/p-preprocess-to-a-file.md) option du compilateur.