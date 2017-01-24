---
title: "Gestion de la m&#233;moire&#160;: exemples | Microsoft Docs"
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
helpviewer_keywords: 
  - "tableaux (C++), allouer des ressources"
  - "tableaux (C++), gestion de la mémoire"
  - "structures de données (C++)"
  - "structures de données (C++), allouer la mémoire"
  - "exemples (MFC), allocation de mémoire"
  - "allocation de frame"
  - "allocation des tas, exemples"
  - "allocation de mémoire (C++), tableaux"
  - "allocation de mémoire (C++), structures de données"
  - "allocation de mémoire (C++), exemples"
  - "allocation de mémoire (C++), objets"
  - "MFC (C++), gestion de la mémoire"
  - "objets (C++), allouer la mémoire"
  - "objets (C++), allocation de mémoire"
  - "allocation de mémoire struct"
  - "types (C++), allocation de mémoire"
ms.assetid: f10240f8-b698-4c83-9288-97a54318930b
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestion de la m&#233;moire&#160;: exemples
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment MFC exécute des allocations et les allocations des segments de trame pour les trois types courants d'allocations de mémoire :  
  
-   [Tableau d'octets.](#_core_allocation_of_an_array_of_bytes)  
  
-   [structures de données](#_core_allocation_of_a_data_structure)  
  
-   [Objet](#_core_allocation_of_an_object)  
  
##  <a name="_core_allocation_of_an_array_of_bytes"></a> Allocation d'un tableau d'octets  
  
#### Pour allouer un tableau d'octets du cadre  
  
1.  Définissez la table désignée par le code suivant.  La table est automatiquement supprimé et sa mémoire est libérée lorsque la variable table se termine son étendue.  
  
     [!code-cpp[NVC_MFC_Utilities#1](../mfc/codesnippet/CPP/memory-management-examples_1.cpp)]  
  
#### Pour allouer un tableau d'octets \(ou d'un type de données primitif\) sur le segment  
  
1.  Utilisez l'opérateur de **new** avec la syntaxe de table affichée dans l'exemple suivant :  
  
     [!code-cpp[NVC_MFC_Utilities#2](../mfc/codesnippet/CPP/memory-management-examples_2.cpp)]  
  
#### Pour libérer les tables du segment  
  
1.  Utilisez l'opérateur de **supprimer** comme suit :  
  
     [!code-cpp[NVC_MFC_Utilities#3](../mfc/codesnippet/CPP/memory-management-examples_3.cpp)]  
  
##  <a name="_core_allocation_of_a_data_structure"></a> Allocation d'une structure de données  
  
#### Pour allouer une structure de données du cadre  
  
1.  Définissez la variable de structure comme suit :  
  
     [!code-cpp[NVC_MFC_Utilities#4](../mfc/codesnippet/CPP/memory-management-examples_4.cpp)]  
  
     La mémoire occupée par la structure est libérée lorsqu'elle se termine son étendue.  
  
#### Pour allouer des structures de données du segment  
  
1.  Utilisez **new** pour allouer les structures de données sur le segment et **supprimer** à libérer, comme indiqué dans les exemples suivants :  
  
     [!code-cpp[NVC_MFC_Utilities#5](../mfc/codesnippet/CPP/memory-management-examples_5.cpp)]  
  
##  <a name="_core_allocation_of_an_object"></a> Allocation d'un objet  
  
#### Pour allouer un objet dans le cadre  
  
1.  Déclarez l'objet comme suit :  
  
     [!code-cpp[NVC_MFC_Utilities#6](../mfc/codesnippet/CPP/memory-management-examples_6.cpp)]  
  
     Le destructeur de l'objet est appelé automatiquement lorsque l'objet se termine son étendue.  
  
#### Pour allouer un objet dans le cadre  
  
1.  Utilisez l'opérateur de **new**, qui retourne un pointeur vers l'objet, pour allouer des objets sur le segment.  Utilisez l'opérateur de **supprimer** à supprimer.  
  
     Les exemples suivants de segments et de cadre supposent que le constructeur d'`CPerson` n'accepte aucun argument.  
  
     [!code-cpp[NVC_MFC_Utilities#7](../mfc/codesnippet/CPP/memory-management-examples_7.cpp)]  
  
     Si l'argument pour le constructeur d'`CPerson` pointeur vers `char`, l'instruction de l'allocation de cadre est :  
  
     [!code-cpp[NVC_MFC_Utilities#8](../mfc/codesnippet/CPP/memory-management-examples_8.cpp)]  
  
     Des instructions pour l'allocation des segments est :  
  
     [!code-cpp[NVC_MFC_Utilities#9](../mfc/codesnippet/CPP/memory-management-examples_9.cpp)]  
  
## Voir aussi  
 [Gestion de la mémoire : allocation de tas](../mfc/memory-management-heap-allocation.md)