---
title: "Assistant Classe C++ g&#233;n&#233;rique | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.class.generic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Classe C++ générique (Assistant) (C++)"
ms.assetid: aa95be9e-fc1b-45db-a11d-0d32c4929077
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Assistant Classe C++ g&#233;n&#233;rique
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ajoute une classe C\+\+ générique à un projet.  La classe n'hérite pas d'ATL ou de MFC.  
  
 **Nom de classe**  
 Définit le nom de la nouvelle classe.  
  
 **fichier .h**  
 Définit le nom du fichier d'en\-tête de la nouvelle classe.  Par défaut, ce nom est fondé sur celui que vous avez entré dans la zone **Nom de la classe**.  Pour enregistrer l'en\-tête de fichier à l'emplacement de votre choix ou pour ajouter la déclaration de classe à un fichier existant, cliquez sur le bouton de sélection \(**...**\).  Si vous spécifiez le nom d'un fichier existant et cliquez sur **Terminer**, l'Assistant vous demande d'indiquer si la déclaration de classe doit être ajoutée au contenu du fichier.  Pour ajouter la déclaration, cliquez sur **Oui** ; cliquez sur **Non** pour revenir à l'Assistant et spécifier un autre nom de fichier.  
  
 **fichier .cpp**  
 Définit le nom du fichier d'implémentation de la nouvelle classe.  Par défaut, ce nom est fondé sur celui que vous avez entré dans la zone **Nom de la classe**.  Cliquez sur le bouton de sélection \(**...**\) pour enregistrer le fichier d'implémentation à l'emplacement de votre choix ou pour ajouter la déclaration de classe à un fichier existant.  Si vous spécifiez le nom d'un fichier existant et cliquez sur **Terminer**, l'Assistant vous demande d'indiquer si la définition de classe doit être ajoutée au contenu du fichier.  Pour ajouter la définition, cliquez sur **Oui** ; cliquez sur **Non** pour revenir à l'Assistant et spécifier un autre nom de fichier.  
  
 **Classe de base**  
 Définit la classe de base de votre nouvelle classe.  
  
 **Accès**  
 Définit l'accès aux membres de la classe de base de votre nouvelle classe.  Les modificateurs d'accès sont des mots clés spécifiant le niveau d'accès des autres classes aux fonctions membres de la classe.  Pour plus d'informations sur la spécification de l'accès, consultez [Contrôle d'accès aux membres](../cpp/member-access-control-cpp.md).  Par défaut, le niveau d'accès de la classe a la valeur `public`.  
  
-   `public`  
  
-   `protected`  
  
-   `private`  
  
-   **Valeur par défaut** \(aucun modificateur d'accès n'est généré.\)  
  
 **Destructeur virtuel**  
 Indique si le destructeur de classe est virtuel.  L'utilisation du destructeur virtuel permet de garantir que le destructeur correct est appelé en cas de suppression d'instances de classes dérivées.  
  
 **Inline**  
 Génère à la fois le constructeur de classe et la définition de classe comme fonctions inline dans le fichier d'en\-tête.  
  
 **Managed**  
 Lorsque la case à cocher est activée, une classe managée et un fichier d'en\-tête sont ajoutés.  Lorsque la case à cocher est désactivée, une classe native et un fichier d'en\-tête sont ajoutés.  
  
## Voir aussi  
 [Ajout d'une classe C\+\+ générique](../ide/adding-a-generic-cpp-class.md)