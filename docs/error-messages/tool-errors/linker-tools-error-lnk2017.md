---
title: "LNK2017 d’erreur des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2017
dev_langs: C++
helpviewer_keywords: LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0f1b588abe7bb222751506e21d90b4b8596b381f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2017"></a>Erreur des outils Éditeur de liens LNK2017
réadressage 'symbole' vers 'segment' non valide sans/LARGEADDRESSAWARE : no  
  
 Vous tentez de créer une image 64 bits avec des adresses 32 bits. Pour ce faire, vous devez :  
  
-   Utilisez une adresse de chargement fixe.  
  
-   Restreindre l’image à 3 Go.  
  
-   Spécifiez [/LARGEADDRESSAWARE : no](../../build/reference/largeaddressaware-handle-large-addresses.md).