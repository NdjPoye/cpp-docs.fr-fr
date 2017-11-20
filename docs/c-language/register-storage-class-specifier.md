---
title: "Spécificateur register de classe de stockage │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- register variables
- register storage class
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 95c06471b7d8ea60754c29a9bde3159174e9c194
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="register-storage-class-specifier"></a>Spécificateur register de classe de stockage
**Section spécifique à Microsoft**  
  
 Le compilateur Microsoft C/C++ n'honore pas les requêtes utilisateur pour les variables de registre. Toutefois, pour la portabilité, toutes les autres sémantiques associées au mot clé **register** sont honorées par le compilateur. Par exemple, vous ne pouvez pas appliquer l'opérateur unaire address-of (**&**) pour enregistrer un objet. De la même manière, le mot clé **register** ne peut pas être utilisé sur les tableaux.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Spécificateurs de classe de stockage pour les déclarations de niveau interne](../c-language/storage-class-specifiers-for-internal-level-declarations.md)