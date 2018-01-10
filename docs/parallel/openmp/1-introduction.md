---
title: 1. Introduction | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c42e72bc-0e31-4b1c-b670-cd82673c0c5a
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f850e236ebfd056da93700df06ec830e5a573284
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="1-introduction"></a>1. Introduction
Ce document spécifie une collection de directives de compilateur, les fonctions de bibliothèque et les variables d’environnement qui peuvent être utilisés pour spécifier le parallélisme de mémoire partagée dans les programmes C et C++. Les fonctionnalités décrites dans ce document sont collectivement appelées le *OpenMP C/C++ Interface API (Application Program)*. L’objectif de cette spécification est pour fournir un modèle de programmation parallèle qui permet à un programme être portable entre les architectures de mémoire partagée à partir de différents fournisseurs. L’API de C/C++ OpenMP prendra en charge par les compilateurs de nombreux fournisseurs. Plus d’informations sur OpenMP, y compris le *OpenMP Fortran Application Program Interface*, sont accessibles sur le site web suivant :  
  
 [http://www.OpenMP.org](http://www.openmp.org)  
  
 Les directives, les fonctions de la bibliothèque et les variables d’environnement définies dans ce document permet aux utilisateurs de créer et gérer des programmes parallèles tout en autorisant la portabilité. Les directives d’étendent le C et modèle de programmation séquentielle C++ avec un seul programme plusieurs constructions de données (SPMD), les constructions de partage de travail et les constructions de synchronisation et qu’ils prennent en charge pour le partage et la privatisation de données. Les compilateurs qui prennent en charge les API C++ OpenMP C inclut une option de ligne de commande du compilateur qui active et autorise l’interprétation de toutes les directives de compilateur OpenMP.