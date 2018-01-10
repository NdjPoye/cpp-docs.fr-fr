---
title: Erreur RW2001 du compilateur de ressources | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RW2001
dev_langs: C++
helpviewer_keywords: RW2001
ms.assetid: 963bdc7d-6ebe-4378-8bbc-47dfcf5d330c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1a14cd36ab87297cf5bc0aa547bdea5ef23260e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rw2001"></a>Erreur RW2001 du compilateur de ressources 
Directive non valide dans le fichier RC prétraité  
  
 Le fichier RC contient un **#pragma** directive.  
  
 Utilisez le **#ifndef** directive de préprocesseur avec la **RC_INVOKED** constante que le compilateur de ressources définit lorsqu’il traite un fichier include. Place le **#pragma** directive à l’intérieur d’un bloc de code qui n’est pas traité lorsque le **RC_INVOKED** constante est définie. Le code dans le bloc est traité exclusivement par le compilateur C/C++ et non par le compilateur de ressources. L’exemple de code suivant illustre cette technique :  
  
```  
#ifndef RC_INVOKED  
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler  
#endif  
```  
  
 Le **#pragma** directive de préprocesseur n’a aucune signification un. Fichier RC. Le **#include** directive de préprocesseur est fréquemment utilisée dans un. Fichier RC pour inclure un fichier d’en-tête (un fichier d’en-tête de personnalisée basée sur le projet ou un fichier d’en-tête standard fourni par Microsoft avec l’un de ses produits). Certains de ces fichiers include contiennent la **#pragma** directive. Un fichier d’en-tête peut contenir un ou plusieurs autres fichiers d’en-tête, le fichier qui contient l’incriminée **#pragma** directive ne peut pas être évidente.  
  
 Le **#ifndef RC_INVOKED** technique peut contrôler l’ajout de fichiers d’en-tête dans les fichiers d’en-tête de projet.