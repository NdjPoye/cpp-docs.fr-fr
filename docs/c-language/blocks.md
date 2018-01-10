---
title: Blocs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- function definitions, blocks in code
- blocks
- compound statements
- statements, compound
ms.assetid: be231a92-c712-464e-ae25-a4becb20f7f5
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 60126db8e2a8f7fe9e56041c4f5b119df828958c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="blocks"></a>Blocs
Une séquence de déclarations, de définitions et d'instructions placées entre accolades (**{ }**) est appelée un « bloc ». Il existe deux types de bloc en C. L'« instruction composée, » une instruction composée d'une ou plusieurs instructions (consultez [L'instruction composée](../c-language/compound-statement-c.md)), est un type de bloc. L’autre, la « définition de fonction », se compose d’une instruction composée (le corps de la fonction) et de l’« en-tête » associé de la fonction (le nom de la fonction, le type de retour et les paramètres formels). Un bloc au sein d'autres blocs est dit « imbriqué ».  
  
 Toutes les instructions composées sont placées entre accolades. En revanche, tous les éléments délimités par des accolades ne constituent pas une instruction composée. Par exemple, bien que les spécifications des éléments de tableau, de structure ou d'énumération puissent apparaître entre accolades, ce ne sont pas des instructions composées.  
  
## <a name="see-also"></a>Voir aussi  
 [Fichiers sources et programmes sources](../c-language/source-files-and-source-programs.md)