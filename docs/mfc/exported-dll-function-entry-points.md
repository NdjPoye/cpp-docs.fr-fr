---
title: "Points d&#39;entr&#233;e de fonction DLL export&#233;e | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exporter des DLL, fonctions"
  - "MFC, gérer des données d'état"
  - "gestion d'état, DLL exportées"
ms.assetid: 3268666e-d24b-44f2-80e8-7c80f73b93ca
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Points d&#39;entr&#233;e de fonction DLL export&#233;e
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour les fonctions exportées d'une DLL, utilisez la macro [AFX\_MANAGE\_STATE](../Topic/AFX_MANAGE_STATE.md) pour maintenir l'état global approprié en basculant du module DLL à la DLL de l'application appelante.  
  
 En cas d'appel, cette macro définit `pModuleState`, un pointeur vers une structure `AFX_MODULE_STATE` contenant des données globales du module, comme l'état du module efficace pour le reste de l'étendue contenante de la fonction.  Lors de la libération de l'étendue contenant la macro, l'état du module efficace précédent est automatiquement restauré.  
  
 Ce basculement est effectué en construisant une instance d'une classe **AFX\_MODULE\_STATE** dans la pile.  Dans le constructeur, cette classe obtient un pointeur vers l'état du module en cours et l'enregistre dans un attribut, puis définit `pModuleState` comme nouvel état du module efficace.  Dans le destructeur, cette classe restaure le pointeur stocké dans un attribut en tant qu'état du module efficace.  
  
 Si vous avez une fonction exportée, telle qu'une qui affiche une boîte de dialogue dans la DLL, vous devez ajouter le code suivant au début de la fonction :  
  
 [!code-cpp[NVC_MFCConnectionPoints#6](../mfc/codesnippet/CPP/exported-dll-function-entry-points_1.cpp)]  
  
 Cela permute l'état du module en cours avec l'état retourné par [AfxGetStaticModuleState](../Topic/AfxGetStaticModuleState.md) jusqu'à la fin de l'étendue actuelle.  
  
 Les problèmes avec des ressources dans les DLL se poseront si la macro `AFX_MANAGE_STATE` n'est pas utilisée.  Par défaut, MFC utilise le handle de ressource d'application principale pour charger le modèle de ressources.  Ce modèle est réellement enregistré dans la DLL.  La cause première est que les informations d'état du module MFC n'ont pas été basculées par la macro `AFX_MANAGE_STATE`.  Le handle de ressources est récupérée de l'état du module MFC.  Ne pas afficher l'état du module provoque l'utilisation du mauvais handle de ressource.  
  
 `AFX_MANAGE_STATE` n'a pas besoin d'être placé dans chaque fonction de la DLL.  Par exemple, `InitInstance` peut être appelé par du code MFC dans l'application sans `AFX_MANAGE_STATE` car MFC déplace automatiquement l'état du module avant `InitInstance` puis les le restaure après que `InitInstance` retourne.  Il en va de même pour tous les gestionnaires de table des messages.  Les DLL normaux ont en fait une procédure spéciale de base de données qui bascule automatiquement l'état du module avant d'acheminer un message.  
  
## Voir aussi  
 [Gestion des données d'état des modules MFC](../mfc/managing-the-state-data-of-mfc-modules.md)