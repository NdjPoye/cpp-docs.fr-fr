---
title: "Personnalisation du traitement de ligne de commande C | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_exec (fonction)"
  - "_setargv (fonction)"
  - "_spawn (fonctions)"
  - "ligne de commande, traiter"
  - "ligne de commande, traiter des arguments"
  - "traitement d'une ligne de commande"
  - "environnement, routine de traitement de l'environnement"
  - "code de démarrage, personnaliser le traitement d'une ligne de commande"
  - "supprimer le traitement de l'environnement"
ms.assetid: c20fa11d-b35b-4f3e-93b6-2cd5a1c3c993
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Personnalisation du traitement de ligne de commande C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si votre programme ne prend pas d'arguments de ligne de commande, vous pouvez économiser une petite quantité d'espace en supprimant l'utilisation de la routine de bibliothèque qui exécute le traitement de ligne de commande.  Cette routine est appelée **\_setargv** \(ou **\_wsetargv** dans l'environnement à caractères larges\), comme décrit dans [Développement les arguments génériques](../c-language/expanding-wildcard-arguments.md).  Pour supprimer son utilisation, définissez une routine qui n'exécute aucune opération dans le fichier contenant la fonction **principale** et nommez\-la **\_setargv** \(ou **\_wsetargv** dans l'environnement à caractères larges\).  L'appel de **\_setargv** ou **\_wsetargv** est ensuite satisfait par votre définition de **\_setargv** ou **\_wsetargv**, et la version de la bibliothèque n'est pas chargée.  
  
 De même, si vous n'accédez jamais à la table d'environnement via l'argument `envp`, vous pouvez fournir votre propre routine vide à utiliser à la place de **\_setenvp** \(ou **\_wsetenvp**\), la routine de traitement de l'environnement.  
  
 Si votre programme effectue des appels à la famille **\_spawn** ou **\_exec** des routines de la bibliothèque Runtime C, vous ne devez pas supprimer la routine de traitement de l'environnement, car cette routine est utilisée pour transmettre un environnement du processus de génération dynamique au nouveau processus.  
  
## Voir aussi  
 [Fonction main et exécution du programme](../c-language/main-function-and-program-execution.md)