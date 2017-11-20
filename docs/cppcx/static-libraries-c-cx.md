---
title: "Bibliothèques statiques (C + c++ / CX) | Documents Microsoft"
ms.custom: 
ms.date: 02/03/2017
ms.prod: windows-client-threshold
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 5f86d24c693cfcd5eecf8b37f0e4567c9c7af3a0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="static-libraries-ccx"></a>Bibliothèques statiques (C++/CX)
Une bibliothèque statique qui est utilisée dans une application de plateforme Windows universelle permettre contenir du code à la norme ISO C++, y compris les types STL et également les appels aux API Win32 qui ne sont pas exclus de la plateforme d’application de plateforme Windows universelle. Une bibliothèque statique consomme des composants Windows Runtime et peut créer des composants Windows Runtime avec certaines restrictions.  
  
## <a name="creating-static-libraries"></a>Création de bibliothèques statiques  
  
#### <a name="to-create-a-static-library-for-use-in-a-universal-windows-platform-app"></a>Pour créer une bibliothèque statique pour une utilisation dans une application de plateforme Windows universelle  
  
1.  Dans la barre de menus, choisissez **fichier** > **nouveau** > **projet** > **bibliothèque statique vide** Windows universel pour les applications de la plateforme.  
  
2.  Dans l' **Explorateur de solutions**, ouvrez le menu contextuel du projet et choisissez **Propriétés**. Dans le **propriétés** boîte de dialogue le **propriétés de Configuration** > **général** , définissez la prise en charge des applications de plateforme Windows universelle  **Oui**.  
  
3.  Sur le **propriétés de Configuration** > **C/C++** , définissez **consommer** Windows Runtime **Extension** à **Oui (/ZW)**.  
  
 Lorsque vous compilez une nouvelle bibliothèque statique, si vous effectuez un appel à une API Win32 qui est exclue pour les applications de plateforme Windows universelle, le compilateur déclenche l’erreur C3861 « Identificateur introuvable ». Pour rechercher une autre méthode qui est pris en charge pour le Windows Runtime, consultez [Alternatives aux API Windows dans les applications du Windows Store](http://msdn.microsoft.com/en-us/75568012-61e0-41cc-a4df-c698f54f21ec).  
  
 Si vous ajoutez un projet de bibliothèque statique C++ à une solution d’application de plateforme Windows universelle, vous devrez peut-être mettre à jour les paramètres de propriété du projet de bibliothèque afin que la propriété de prise en charge de plateforme Windows universelle est définie **Oui**. Sans ce paramètre, le code est généré et crée des liens, mais une erreur se produit lorsque vous essayez de vérifier l'application pour [!INCLUDE[win8_appstore_long](../cppcx/includes/win8-appstore-long-md.md)]. La bibliothèque statique doit être compilée avec les mêmes paramètres de compilateur que ceux du projet qui la consomme.  
  
 Si vous consommez une bibliothèque statique qui crée des classes `ref` publiques, des classes d'interface publiques ou des classes de valeur publiques, l'éditeur de liens déclenche l'avertissement suivant :  
  
> **avertissement LNK4264 :** archivage du fichier objet compilé avec /ZW dans une bibliothèque statique ; Notez que lors de la création des types Windows Runtime, il n'est pas recommandée pour créer un lien avec une bibliothèque statique qui contient des métadonnées Windows Runtime.  
  
 Vous pouvez ignorer l’avertissement uniquement si la bibliothèque statique ne produise pas les composants Windows Runtime qui sont consommés en dehors de la bibliothèque elle-même. Si la bibliothèque ne consomme pas un composant qu'elle définit, l'éditeur de liens peut optimiser l'implémentation même si les métadonnées publiques contiennent les informations de type. En d'autres termes, les composants publics d'une bibliothèque statique sont compilés mais ne sont pas activés au moment de l'exécution. Pour cette raison, un composant Windows Runtime qui est destiné à la consommation par d’autres composants ou les applications doit être implémenté dans une bibliothèque de liens dynamiques (DLL).  
  
## <a name="see-also"></a>Voir aussi  
 [Thread et Marshaling](../cppcx/threading-and-marshaling-c-cx.md)