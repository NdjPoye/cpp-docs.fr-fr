---
title: Assistant classe C++ générique | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.class.generic
dev_langs:
- C++
helpviewer_keywords:
- Generic C++ Class Wizard [C++]
ms.assetid: aa95be9e-fc1b-45db-a11d-0d32c4929077
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43e86a4047ef025f49dd01eda90f324623a90752
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="generic-c-class-wizard"></a>Assistant Classe C++ générique
Ajoute une classe C++ générique à un projet. La classe n’hérite pas d’ATL ou MFC.  
  
 **Nom de classe**  
 Définit le nom de la nouvelle classe.  
  
 **fichier .h**  
 Définit le nom du fichier d’en-tête pour la nouvelle classe. Par défaut, ce nom est basé sur le nom que vous fournissez dans **nom de la classe**. Pour enregistrer le fichier d’en-tête à l’emplacement de votre choix, ou pour ajouter la déclaration de classe à un fichier existant, cliquez sur le bouton de sélection (**...** ). Si vous spécifiez un fichier existant, lorsque vous cliquez sur **Terminer**, l’Assistant vous invite à indiquer si la déclaration de classe doit être ajoutée au contenu du fichier. Pour ajouter la déclaration, cliquez sur **Oui**; pour revenir à l’Assistant et spécifiez un autre nom de fichier, cliquez sur **non**.  
  
 **fichier .cpp**  
 Définit le nom du fichier d’implémentation pour la nouvelle classe. Par défaut, ce nom est basé sur le nom que vous fournissez dans **nom de la classe**. Pour enregistrer le fichier d’implémentation à l’emplacement de votre choix, ou pour ajouter la définition de classe à un fichier existant, cliquez sur le bouton de sélection (**...** ). Si vous spécifiez un fichier existant, lorsque vous cliquez sur **Terminer**, l’Assistant vous invite à indiquer si la définition de classe doit être ajoutée au contenu du fichier. Pour ajouter la définition, cliquez sur **Oui**; pour revenir à l’Assistant et spécifiez un autre nom de fichier, cliquez sur **non**.  
  
 **Classe de base**  
 Définit la classe de base pour la nouvelle classe.  
  
 **Accès**  
 Définit l’accès aux membres de la classe de base pour la nouvelle classe. Modificateurs d’accès sont des mots clés qui spécifient le niveau d’accès dont disposent d’autres classes pour les fonctions membres de classe. Pour plus d’informations sur la façon de spécifier l’accès, consultez [contrôle d’accès de membre](../cpp/member-access-control-cpp.md). Par défaut, le niveau d’accès de classe a la valeur `public`.  
  
-   `public`  
  
-   `protected`  
  
-   `private`  
  
-   **Par défaut** (aucun modificateur d’accès n’est généré.)  
  
 **Destructeur virtuel**  
 Spécifie si le destructeur de classe est virtuel. Utilisation d’un destructeur virtuel permet de garantir que le destructeur correct est appelé lors de la suppression d’instances de classes dérivées.  
  
 **Inline**  
 Génère le constructeur de classe et la définition de classe en tant que fonctions inline dans le fichier d’en-tête.  
  
 **Géré**  
 Lorsque sélectionnée, ajoute un fichier de classe et d’en-tête géré. Lorsqu’elle est désactivée, ajoute un fichier de classe et d’en-tête natif.  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout d’une classe C++ générique](../ide/adding-a-generic-cpp-class.md)