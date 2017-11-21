---
title: "Mettre à jour une colonne quand une autre table contient une référence à la ligne | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cac57f2f4a1175fa1d9f4009e10fd3d0fae2a3b0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>Mise à jour d'une colonne quand une autre table contient une référence à la ligne
Certains fournisseurs peuvent détecter les colonnes dans la modification de ligne, mais pas de nombreux fournisseurs. Par conséquent, la mise à jour d’une colonne peut entraîner une erreur lorsqu’il existe une référence à la ligne que vous tentez de mettre à jour. Pour résoudre ce problème, créez un accesseur séparé contenant uniquement les colonnes que vous souhaitez modifier. Transmettre le numéro de cet accesseur à `SetData`.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation des accesseurs](../../data/oledb/using-accessors.md)