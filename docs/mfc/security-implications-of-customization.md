---
title: "Implications en matière de sécurité de personnalisation | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- security, MFC Feature Pack
- MFC Feature Pack, security
ms.assetid: 9be96b12-be38-43bd-a133-5d671265f7a1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b408b4595e95016323d2b43f1ed51fc6e2e6d244
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="security-implications-of-customization"></a>Implications en matière de sécurité de la personnalisation
Cette rubrique présente une faille de sécurité potentielle dans MFC.  
  
## <a name="potential-security-weakness"></a>Faille de sécurité potentielle  
 MFC permet à l’utilisateur de personnaliser l’apparence d’une interface utilisateur d’applications, par exemple, l’apparence des boutons et des icônes. MFC prend également en charge les outils définis par l’utilisateur, qui permettent à l’utilisateur d’exécuter des commandes shell. Une faille de sécurité se produit car les paramètres personnalisés de l’application sont enregistrées dans le profil utilisateur dans le Registre. Toute personne qui peut accéder au Registre permettre modifier ces paramètres et modifier l’apparence d’application ou le comportement. Par exemple, un administrateur sur l’ordinateur peut emprunter l’identité utilisateur en forçant l’application de l’utilisateur d’exécuter des programmes arbitraires (même à partir d’un partage réseau).  
  
## <a name="workarounds"></a>Solutions  
 Nous vous recommandons d’une des trois manières de fermer les vulnérabilités dans le Registre :  
  
-   Chiffrer les données qui y sont stockées  
  
-   Stocker les données dans un fichier sécurisé au lieu de dans le Registre.  
  
     Pour effectuer l’une de ces deux premières méthodes, dérivez une classe de [classe CSettingsStore](../mfc/reference/csettingsstore-class.md) et substituer ses méthodes pour implémenter le chiffrement ou le stockage en dehors du Registre.  
  
-   Vous pouvez également désactiver des personnalisations dans votre application.  
  
## <a name="see-also"></a>Voir aussi  
 [Personnalisation pour MFC](../mfc/customization-for-mfc.md)

