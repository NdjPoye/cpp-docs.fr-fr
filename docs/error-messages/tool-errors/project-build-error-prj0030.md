---
title: "PRJ0030 d’erreur de Build de projet | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0030
dev_langs: C++
helpviewer_keywords: PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b6fe537dd8e6705fd5e30929a2480eb1d9ef9119
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0030"></a>Erreur de génération de projet PRJ0030
Erreur d’expansion macro. Récurrence d’évaluation a dépassé 32 niveaux pour $(macro).  
  
 Cette erreur est due à la récursivité dans vos macros. Par exemple, si vous définissez la **répertoire intermédiaire** propriété (voir [général, Page de propriétés (projet)](../../ide/general-property-page-project.md)) $ (IntDir), vous devez la récursivité.  
  
 Pour résoudre cette erreur, ne définissez pas les propriétés en termes de macros que qui sont utilisées pour définir ou macros.