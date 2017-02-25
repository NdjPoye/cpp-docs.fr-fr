---
title: "Erreur irr&#233;cup&#233;rable RC1052 du compilateur de ressources  | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC1052"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1052"
ms.assetid: 59803673-492b-44fa-80fa-df93b8aaf9fb
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur irr&#233;cup&#233;rable RC1052 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

limite du compilateur : blocs \#if ou \#ifdef imbriqués trop profondément  
  
 Le programme a dépassé le nombre maximal de niveaux d'imbrication autorisés pour les directives `#if` et `#ifdef`.  
  
 Cette erreur peut être provoquée par des fichiers include qui utilisent ces directives de préprocesseur.  
  
 Pour résoudre ce problème, réduisez le nombre de directives `#if` et `#ifdef` imbriquées dans votre fichier de ressources.  Si le problème est provoqué par les fichiers d'en\-tête inclus dans votre fichier de ressources, réduisez le nombre de directives `#if` et `#ifdef` imbriquées dans les fichiers d'en\-tête.  Si ce n'est pas possible, créez un fichier d'en\-tête et incluez\-le dans votre fichier de ressources, en exécutant le préprocesseur sur les fichiers d'en\-tête inclus existants.  Pour plus d'informations, consultez l'option de compilateur [\/P \(Prétraiter jusqu'à un fichier\)](../../build/reference/p-preprocess-to-a-file.md).