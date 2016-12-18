---
title: "C.2 R&#232;gles | Microsoft Docs"
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
ms.assetid: 4d52fef7-3eb7-4480-a335-8ed48681092b
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C.2 R&#232;gles
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La notation est décrite dans la section 6.1 de la norme C. Cette annexe grammaire indique les extensions à la grammaire du langage de base pour les directives OpenMP C et C++.  
  
 **/\* en C++ (ISO/IEC 14882:1998) \*/**  
  
 *instruction-seq*:  
  
 *instruction*  
  
 *directive OpenMP*  
  
 *instruction de déclaration-seq*  
  
 *instruction-seq directive openmp*  
  
 **/\* dans C90 (ISO/CEI 9899 : 1990) \*/**  
  
 *liste d’instructions*:  
  
 *instruction*  
  
 *directive OpenMP*  
  
 *instruction-list, instruction*  
  
 *liste d’instructions de la directive openmp*  
  
 **/\* dans la norme C99 (ISO/IEC 9899:1999) \*/**  
  
 *élément de bloc*:  
  
 *déclaration*  
  
 *instruction*  
  
 *directive OpenMP*  
  
 *instruction*:  
  
 **/\* instructions standards \*/**  
  
 *construction d’OpenMP*  
  
 *construction d’OpenMP*:  
  
 *construction parallèle*  
  
 *construction for*  
  
 *construction de sections*  
  
 *construction d’unique*  
  
 *parallèle-construction for*  
  
 *construction de sections parallèles*  
  
 *maître-construc*  
  
 *construction Critical*  
  
 *construction atomic*  
  
 *construction commandée*  
  
 *la directive OpenMP*:  
  
 *directive Barrier*  
  
 *directive du vidage*  
  
 *bloc structuré*:  
  
 *instruction*  
  
 *construction parallèle*:  
  
 *bloc structuré directive parallèle*  
  
 *directive parallèle*:  
  
 **# pragma omp parallel**  *parallèle-clause*optseq *nouvelle ligne*  
  
 *clause parallèle*:  
  
 *clause unique parallèle*  
  
 *clause de données*  
  
 *clause unique parallèle*:  
  
 **Si (** *expression* **)**  
  
 **num_threads (** *expression* **)**  
  
 *construction for*:  
  
 *instruction d’itération pour (directive)*  
  
 *directive pour*:  
  
 **# pragma omp pour** *clause for*optseq *nouvelle ligne*  
  
 *clause for*:  
  
 *unique pour la clause*  
  
 *clause de données*  
  
 **NOWAIT**  
  
 *unique pour la clause*:  
  
 **commandée**  
  
 **planification (** *-type de planification* **)**  
  
 **planification (** *-type de planification* **,** *expression* **)**  
  
 *type de planification*:  
  
 **statique**  
  
 **dynamique**  
  
 **Interactive**  
  
 **exécution**  
  
 *construction de sections*:  
  
 *portée de section-sections (directive)*  
  
 *directive de sections*:  
  
 **sections de # pragma omp** *sections clause*optseq *nouvelle ligne*  
  
 *clause de sections*:  
  
 *clause de données*  
  
 **NOWAIT**  
  
 *étendue de la section*:  
  
 *{section-séquence}*  
  
 *séquence de la section*:  
  
 *la directive de la section*opt *bloc structuré*  
  
 *séquence de section section directive structuré bloc*  
  
 *la directive de la section*:  
  
 **# pragma omp section** *nouvelle ligne*  
  
 *simple-construction*:  
  
 *bloc structuré directive unique*  
  
 *la directive du seul*:  
  
 **# pragma omp unique** *une clause unique*optseq *nouvelle ligne*  
  
 *clause unique*:  
  
 *clause de données*  
  
 **NOWAIT**  
  
 *construction parallèle-for*:  
  
 *instruction d’itération parallèle pour (directive)*  
  
 *-parallèle pour la directive*:  
  
 **# pragma omp parallel pour** *parallèle de clause for*optseq *nouvelle ligne*  
  
 *parallèle de clause for*:  
  
 *clause unique parallèle*  
  
 *unique pour la clause*  
  
 *clause de données*  
  
 *construction de sections parallèles*:  
  
 *portée de section parallèle-sections (directive)*  
  
 *directive de sections parallèles*:  
  
 **sections de # pragma omp parallel** *parallèle-sections-clause*optseq *nouvelle ligne*  
  
 *sections parallèle-clause*:  
  
 *clause unique parallèle*  
  
 *clause de données*  
  
 *construction de master*:  
  
 *bloc structuré de directive de master*  
  
 *directive de master*:  
  
 **masque de # pragma omp** *nouvelle ligne*  
  
 *construction Critical*:  
  
 *bloc structuré critiques (directive)*  
  
 *directive Critical*:  
  
 **# pragma omp critiques** *une expression de la région*opt *nouvelle ligne*  
  
 *une expression de la région*:  
  
 *(identificateur)*  
  
 *la directive de la barrière*:  
  
 **barrière de # pragma omp** *nouvelle ligne*  
  
 *construction atomic*:  
  
 *instruction d’expression directive atomic*  
  
 *directive atomic*:  
  
 **# pragma omp atomic** *nouvelle ligne*  
  
 *directive Flush*:  
  
 **# pragma omp vidage** *flush-var*opt *nouvelle ligne*  
  
 *Flush-var*:  
  
 *(liste de variable)*  
  
 *construction ordonnée*:  
  
 *bloc structuré directive commandée*  
  
 *directive commandée*:  
  
 **# pragma omp commandée** *nouvelle ligne*  
  
 *déclaration*:  
  
 **/\* déclarations standards \*/**  
  
 *directive threadprivate*  
  
 *la directive threadprivate*:  
  
 **# pragma omp threadprivate (** *liste de variable*  **)** *nouvelle ligne*  
  
 *clause de données*:  
  
 **Private (** *liste de variable* **)**  
  
 **copyprivate (**  *liste de variable*  **)**  
  
 **firstprivate (**  *liste de variable*  **)**  
  
 **lastprivate (** *liste de variable*  **)**  
  
 **partagé (** *liste de variable* **)**  
  
 **par défaut (partagée)**  
  
 **par défaut (aucun)**  
  
 **réduction (**  *-opérateur de réduction*  **:**  *liste de variable*  **)**  
  
 **copyin (**  *liste de variable*  **)**  
  
 *opérateur de réduction*:  
  
 *Un des*: **+ \* -& ^ & #124 ; & & & #124 ; & #124 ;**  
  
 **/\* en C \*/**  
  
 *liste de la variable*:  
  
 *Identificateur*  
  
 *liste de la variable* **,** *identificateur*  
  
 **/\* en C++ \*/**  
  
 *liste de la variable*:  
  
 *expression de code*  
  
 *liste de la variable* **,** *id-expression*