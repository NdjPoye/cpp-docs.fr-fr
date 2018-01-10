---
title: "Sérialisation : Sérialisation d’un objet | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- serializing objects [MFC]
- serialization [MFC], objects
- objects [MFC], serializing
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 37e688a3619cd203e61997999a9b7eb7651d73fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="serialization-serializing-an-object"></a>Sérialisation : sérialisation d'un objet
L’article [sérialisation : définir une classe sérialisable](../mfc/serialization-making-a-serializable-class.md) montre comment rendre une classe sérialisable. Une fois que vous avez une classe sérialisable, vous pouvez sérialiser des objets de cette classe vers et à partir d’un fichier via un [CArchive](../mfc/reference/carchive-class.md) objet. Cet article explique :  
  
-   [Un objet CArchive est](../mfc/what-is-a-carchive-object.md).  
  
-   [Deux façons de créer un objet CArchive](../mfc/two-ways-to-create-a-carchive-object.md).  
  
-   [Comment utiliser CArchive <\< et >> opérateurs](../mfc/using-the-carchive-output-and-input-operators.md).  
  
-   [Le stockage et chargement d’objets CObject via une archive](../mfc/storing-and-loading-cobjects-via-an-archive.md).  
  
 Vous pouvez laisser l’infrastructure de création de l’archive de votre document sérialisable ou de créer explicitement le `CArchive` vous-même de l’objet. Vous pouvez transférer des données entre un fichier et l’objet sérialisable à l’aide de la <\< et >> opérateurs pour `CArchive` ou, dans certains cas, en appelant le `Serialize` fonction d’un `CObject`-classe dérivée.  
  
## <a name="see-also"></a>Voir aussi  
 [Sérialisation](../mfc/serialization-in-mfc.md)

