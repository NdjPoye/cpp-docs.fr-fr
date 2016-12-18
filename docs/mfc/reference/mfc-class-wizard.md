---
title: "Classe MFC (Assistant) | Microsoft Docs"
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
  - "vc.wizards.classwizard"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Classe MFC (Assistant)"
  - "Assistants (MFC)"
ms.assetid: 8b0dd867-5d07-4214-99be-2a1c1995e6d9
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe MFC (Assistant)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous permet d'ajouter des messages et des gestionnaires de messages aux classes dans votre projet.  Vous pouvez également démarrer d'autres Assistants ou ajouter une classe à votre projet.  
  
 Pour ouvrir l'**Assistant Classe MFC**, sur le menu **Projet**, cliquez sur **Assistant Classe**.  Pour ouvrir l'Assistant avec un raccourci clavier, tapez CTRL\+MAJ\+X.  
  
## Liste UIElement  
 **Projet**  
 Nom d'un projet de votre solution.  
  
 Vous pouvez choisir d'autres projets de votre solution dans la zone de liste déroulante.  
  
 **Nom de classe**  
 Nom d'une classe de votre projet.  
  
 Lorsque vous sélectionnez une classe dans la liste **Nom de la classe**, les données de la classe remplissent les contrôles dans l'**Assistant Classe MFC**.  Lorsque vous modifiez la valeur d'un contrôle, les données dans la classe sélectionnée sont affectées.  
  
 **Ajouter la classe**  
 Vous permet d'ajouter une classe de plusieurs sources.  
  
 Selon votre sélection, l'**Assistant Ajouter une classe MFC**, **Assistant Ajout de classes d'une Typelib**, **Assistant Ajout d'une classe à partir d'un contrôle ActiveX**, ou **Assistant Consommateur ODBC MFC** est démarré.  
  
 **Classe de base**  
 Classe de base de la classe affichée dans **Nom de la classe**.  
  
 **Déclaration de classe**  
 Classe dans laquelle la classe **Nom de la classe** est déclarée.  
  
 La zone **Déclaration de classe** s'affiche uniquement si le nom qu'elle contient diffère du nom indiqué dans **Implémentation de classe**.  
  
 **Ressource**  
 ID de la ressource figurant dans **Nom de la classe**, le cas échéant.  Sinon, la zone **Ressource** est vide.  
  
 **Implémentation de classe**  
 Nom du fichier qui contient l'implémentation de la classe indiquée dans **Nom de la classe**.  
  
 Vous pouvez sélectionner un fichier d'implémentation différent en cliquant sur la flèche.  Le tableau suivant répertorie les options disponibles.  
  
|Option|Description|  
|------------|-----------------|  
|**Ouvrir un fichier**|Quitte l'Assistant de classe et ouvre le fichier en cours de l'implémentation de classe.|  
|**Ouvrir le dossier contenant**|Ouvre le dossier qui contient le fichier d'implémentation de classe actuel.|  
|**Copier le chemin d'accès complet vers le presse\-papiers**|Copie le chemin d'accès du fichier d'implémentation actuel vers le Presse\-papiers.|  
  
 **Commandes**  
 Vous permet d'ajouter, supprimer, modifier ou rechercher une commande et son gestionnaire de messages.  
  
 Pour ajouter un gestionnaire, cliquez sur **Ajouter un gestionnaire** ou double\-cliquez sur un élément dans la liste **ID d'objets** ou **Messages**.  Le nom de fonction, l'ID et le message résultants s'affichent dans la liste **Fonctions membres**.  
  
 Pour supprimer un gestionnaire, sélectionnez un élément dans la liste **Fonctions membres** puis cliquez sur **Supprimer le gestionnaire**.  
  
 Pour modifier un gestionnaire, double\-cliquez sur l'élément correspondant dans la liste **Fonctions membres**.  Ou sélectionnez un élément dans la zone de liste, puis cliquez **Modifier le code**.  
  
 **Messages**  
 Vous permet d'ajouter, supprimer, modifier ou rechercher un message et son gestionnaire de messages.  
  
 Pour ajouter un gestionnaire, cliquez sur **Ajouter un gestionnaire** ou double\-cliquez sur un élément dans la liste **Messages**.  
  
 Pour ajouter un message personnalisé, cliquez sur **Ajouter un message personnalisé** ou appuyez sur Entrée, puis spécifiez des valeurs dans la boîte de dialogue **Ajouter un message personnalisé**.  Dans cette boîte de dialogue, vous pouvez également sélectionner **Message inscrit** pour gérer un nouveau message de fenêtre garanti pour être unique dans tout le système d'exploitation.  
  
 **Fonctions virtuelles**  
 Vous permet d'ajouter, supprimer, modifier ou rechercher une fonction virtuelle, ou une fonction virtuelle substituée.  
  
 **Variables membres**  
 Vous permet d'ajouter, supprimer, modifier ou rechercher une variable membre.  
  
 **Méthodes**  
 Vous permet d'ajouter, supprimer ou rechercher une méthode, et également d'atteindre la définition ou la déclaration d'une méthode.  
  
 Pour ajouter une méthode, cliquez sur **Ajouter une méthode**, puis spécifiez des valeurs dans la boîte de dialogue **Ajouter une méthode**.  
  
 Pour supprimer une méthode, sélectionnez un élément dans la liste **Méthodes** puis cliquez sur **Supprimer la méthode**.  
  
 Pour afficher une déclaration, sélectionnez un élément dans la liste **Méthodes** puis cliquez sur **Atteindre la déclaration.**  
  
 Pour afficher une définition, double\-cliquez sur un élément dans la liste **Méthodes**.  Ou sélectionnez un élément dans la liste **Méthodes**, puis cliquez le bouton **Atteindre la définition**.  
  
## Voir aussi  
 [Ajout d'une classe](../../ide/adding-a-class-visual-cpp.md)