---
title: "Création de Scripts pour ATL (inscription) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- scripting, registry scripting
- ATL, registry
- registrar scripts [ATL]
- scripts, Registrar scripts
- scripts, creating
ms.assetid: cbd5024b-8061-4a71-be65-7fee90374a35
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b3bda4043693d14451a2de14cbc71fbecdcdddba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-registrar-scripts"></a>Creating Registrar Scripts
Un script registrar offre piloté par les données, plutôt que de piloté par les API, l’accès au Registre du système. Accès piloté par les données est généralement plus efficace, car il accepte uniquement une ou deux lignes dans un script pour ajouter une clé au Registre.  
  
 Le [Assistant contrôle ATL](../atl/reference/atl-control-wizard.md) génère automatiquement un script registrar pour votre serveur COM. Vous trouverez ce script dans le fichier .rgs associé à votre objet.  
  
 Moteur de Script d’ATL Registrar traite votre script registrar au moment de l’exécution. ATL appelle automatiquement le moteur de Script lors de l’installation du serveur.  
  
 Cet article couvre les rubriques suivantes liées aux scripts registrar :  
  
-   [Présentation de la syntaxe BNF (Backus Nauer Form)](../atl/understanding-backus-nauer-form-bnf-syntax.md)  
  
-   [Présentation des arborescences d’analyse](../atl/understanding-parse-trees.md)  
  
-   [Exemples de scripts du Registre](../atl/registry-scripting-examples.md)  
  
-   [Utilisation de paramètres remplaçables (préprocesseur d’inscription)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)  
  
-   [Appel de scripts](../atl/invoking-scripts.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Composant de Registre (inscription)](../atl/atl-registry-component-registrar.md)

