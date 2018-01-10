---
title: "Propriété de touche accélérateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Key property
ms.assetid: d1570cd9-b414-4cd6-96bd-47c38281eaca
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 365960717f5fe4cedf79615fd3087bc89d6b531c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="accelerator-key-property"></a>Key, propriété d'un accélérateur
Les entrées valides pour la propriété de clé dans la table d’accélérateurs sont les suivantes :  
  
-   Nombre entier compris entre 0 et 255 au format décimal. La valeur détermine si la valeur est traitée comme ASCII ou ANSI comme suit :  
  
    -   Les nombres à un chiffre sont toujours interprétées comme la clé correspondante, plutôt que comme des valeurs ASCII ou ANSI.  
  
    -   Valeurs comprises entre 1 et 26, lorsque précédé par des zéros, sont interprétées comme ^ A à ^ Z, qui représente la valeur ASCII des lettres de l’alphabet lorsque la touche CTRL enfoncée.  
  
    -   Valeurs comprises entre 27-32 sont toujours interprétées en tant que valeurs de trois chiffres décimaux 027 et 032.  
  
    -   Les valeurs 033 à 255, précédé de 0 ou ne sont pas interprétées comme des valeurs ANSI.  
  
-   Un caractère unique du clavier. Majuscules de A - Z ou de nombres 0 - 9 peuvent être ASCII ou des valeurs de clé virtuels ; tout autre caractère est ASCII uniquement.  
  
-   Un caractère du clavier unique dans la plage A - Z (majuscules uniquement), précédé d’un signe insertion (^) (par exemple, ^ C). Cela passe à la valeur ASCII de la clé lorsqu’elle est enfoncée avec la touche CTRL enfoncée.  
  
    > [!NOTE]
    >  Lorsque vous entrez une valeur ASCII, les options de la propriété modifier sont limitées. La seule clé de contrôle disponible pour une utilisation est la touche ALT ENFONCÉE.  
  
-   N’importe quel identificateur valid de touche virtuelle. La boîte de clé de liste déroulante dans la table d’accélérateurs contient une liste des identificateurs de clé virtuels standards.  
  
    > [!TIP]
    >  Une autre façon de définir une touche accélérateur est de clic droit sur une entrée ou plusieurs entrées dans la table d’accélérateurs, choisissez **enfoncée suivante** dans le menu contextuel, puis appuyez sur un des serveurs cibles ou des combinaisons de touches du clavier. Le **enfoncée suivante** commande est également disponible à partir de la **modifier** menu.  
  
## <a name="requirements"></a>Configuration requise  
 Win32  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des propriétés d’un accélérateur](../windows/setting-accelerator-properties.md)   
 [Modification d’une table d’accélérateurs](../windows/editing-in-an-accelerator-table.md)   
 [Éditeur d’accélérateurs](../windows/accelerator-editor.md)