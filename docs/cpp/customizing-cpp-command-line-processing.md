---
title: "Personnalisation du traitement de ligne de commande C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_setenvp"
  - "_setargv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_setargv (fonction)"
  - "_setenvp (fonction)"
  - "ligne de commande, traiter"
  - "ligne de commande, traiter des arguments"
  - "traitement d'une ligne de commande"
  - "environnement, routine de traitement de l'environnement"
  - "code de démarrage, personnaliser le traitement d'une ligne de commande"
  - "supprimer le traitement de l'environnement"
ms.assetid: aae01cbb-892b-48b8-8e1f-34f22421f263
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Personnalisation du traitement de ligne de commande C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Si votre programme ne prend pas d'arguments de ligne de commande, vous pouvez économiser une petite quantité d'espace en supprimant l'utilisation de la routine de bibliothèque qui exécute le traitement de ligne de commande.  Cette routine est appelée **\_setargv** et est décrite dans la section [Développement des caractères génériques](../cpp/wildcard-expansion.md).  Pour supprimer son utilisation, définissez une routine qui n'exécute aucune opération dans le fichier contenant la fonction **main**, puis nommez \-la **\_setargv**.  L'appel à **\_setargv** est ensuite satisfait par votre définition de **\_setargv**, et la version de la bibliothèque n'est pas chargée.  
  
 De même, si vous n'accédez jamais à la table d'environnement via l'argument `envp`, vous pouvez fournir votre propre routine vide à utiliser à la place de **\_setenvp**, la routine de traitement de l'environnement.  Comme avec la fonction **\_setargv**, **\_setenvp** doit être déclaré comme **extern "C"**.  
  
 Votre programme peut effectuer des appels à la famille de routines **spawn** ou `exec` dans la bibliothèque Runtime C.  Le cas échéant, vous ne devez pas supprimer la routine de traitement de l'environnement, car cette routine est utilisée pour transmettre un environnement du processus parent au processus enfant.  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [main : démarrage du programme](../cpp/main-program-startup.md)