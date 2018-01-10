---
title: "LNK4014 d’avertissement des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4014
dev_langs: C++
helpviewer_keywords: LNK4014
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8e0e0e87fb9c8e6006c62e07b7bb9b6435a22dd3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4014"></a>Avertissement des outils Éditeur de liens LNK4014
Impossible de trouver l’objet membre « %{ObjectName/} »  
  
 LIB n’a pas pu trouver `objectname` dans la bibliothèque.  
  
 Le **/suppression de** et **/extraire** options requièrent le nom complet de l’objet membre qui doit être supprimé ou copié vers un fichier. Le nom complet inclut le chemin d’accès du fichier objet d’origine. Pour afficher les noms complets des objets membres d’une bibliothèque, utilisez DUMPBIN [/ARCHIVEMEMBERS](../../build/reference/archivemembers.md) ou LIB [/liste](../../build/reference/managing-a-library.md).