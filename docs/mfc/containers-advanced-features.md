---
title: "Conteneurs&#160;: fonctionnalit&#233;s avanc&#233;es | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "applications conteneur/serveur (C++)"
  - "conteneurs (C++), fonctionnalités avancées"
  - "conteneurs (C++), applications conteneur"
  - "conteneurs (C++), liens vers les objets OLE incorporés"
  - "objets incorporés (C++)"
  - "liens (C++), vers des objets OLE incorporés"
  - "conteneurs OLE, fonctionnalités avancées"
  - "contrôles OLE, conteneurs"
  - "applications serveur/conteneur"
ms.assetid: 221fd99c-b138-40fa-ad6a-974e3b3ad1f8
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Conteneurs&#160;: fonctionnalit&#233;s avanc&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article décrit les étapes nécessaires pour intégrer des fonctionnalités avancées optionnelles dans des applications de conteneur existantes.  Ces fonctionnalités sont :  
  
-   [Une application qui est à la fois un conteneur et un serveur](#_core_creating_a_container.2f.server_application)  
  
-   [un lien OLE vers un objet incorporé](#_core_links_to_embedded_objects)  
  
##  <a name="_core_creating_a_container.2f.server_application"></a> Créer une application conteneur\/serveur  
 Une application conteneur\/serveur est une application qui joue à la fois le rôle de conteneur et de serveur.  Microsoft Word pour Windows en est un exemple.  Vous pouvez inclure Word dans d'autres applications, vous pouvez également inclure des éléments dans Word pour les documents Windows.  Le processus pour modifier votre application de conteneurs pour qu'elle soit à la fois un un conteneur et un serveur complet \(vous ne pouvez pas créer d'application combinaison conteneurs\/miniserver\) est semblable au processus de création d'un serveur complet.  
  
 L'article [Serveurs : Implémenter un serveur](../mfc/servers-implementing-a-server.md) répertorie plusieurs tâches requises pour implémenter une application serveur.  Si vous convertissez une application conteneur en une application conteneur\/serveur, vous devez effectuer certaines de ces mêmes tâches, ajoutant du code au conteneur.  Ce qui suit répertorie les éléments importants à prendre en compte :  
  
-   Le code de conteneur créé par l'Application initialise déjà le sous\-système OLE.  Vous n'aurez besoin de modifier ou ajouter quoi que ce soit pour ce support.  
  
-   Où la classe de base d'une classe de document est `COleDocument`, remplacez la classe de base en `COleServerDoc`.  
  
-   Remplacez `COleClientItem::CanActivate` pour éviter de modifier des éléments en place lorsque le serveur lui\-même permet de modifier sur place.  
  
     Par exemple, l'exemple [OCLIENT](../top/visual-cpp-samples.md) MFC OLE a incorporé un élément créé par votre application conteneur\/serveur.  Vous ouvrez l'application OCLIENT et modifiez sur place l'élément créé par votre application conteneur\/serveur.  Lors de la modification de l'élément de votre application, vous décidez que vous voulez inclure un élément créé par l'exemple [HIERSVR](../top/visual-cpp-samples.md) MFC OLE.  Pour cela, vous ne pouvez pas utiliser l'activation sur place.  Vous devez entièrement ouvrir HIERSVR pour activer cet élément.  Comme la bibliothèque MFC ne prend pas en charge cette fonctionnalité OLE, remplacer `COleClientItem::CanActivate` vous permet de contrôler cette situation et empêcher une erreur d'exécution possible dans votre application.  
  
 Si vous créez une application et souhaitez qu'elle s'exécute en tant qu'application conteneur\/serveur, choisissez l'option dans OLE la boîte de dialogue options dans l'Application et la prise en charge est créée automatiquement.  Pour plus d'informations, consultez l'article [Vue d'ensemble : Créer un conteneur de contrôles ActiveX](../mfc/reference/creating-an-mfc-activex-control-container.md).  Pour plus d'informations sur les exemples de MFC, consultez les exemples MFC.  
  
 Notez que vous ne pouvez pas insérer une application MDI en elle\-même.  Une application qui est un conteneur\/serveur ne peut pas être insérée dans elle\-même à moins qu'elle soit une application de SDI.  
  
##  <a name="_core_links_to_embedded_objects"></a> liens vers les objets incorporés  
 Liens vers la fonction d'objets incorporés permet à un utilisateur de créer un document avec un lien OLE vers un objet incorporé dans votre application conteneur.  Par exemple, créez un document dans un traitement de texte contenant une feuille de calcul incorporée.  Si votre application prend en charge les liens vers des objets incorporés, elle pourrait également coller un lien vers la feuille de calcul contenus dans le document de traitement de texte.  Cette fonctionnalité permet à votre application d'utiliser les informations contenues dans la feuille de calcul sans savoir où le traitement de texte l'a initialement obtenue.  
  
#### Lier vers des objets incorporés dans votre application  
  
1.  Dérivez votre classe de document de `COleLinkingDoc` au lieu de `COleDocument`.  
  
2.  Créez un ID de classe \(**CLSID**\) pour votre application à l'aide du générateur d'ID de classe inclus avec les outils de développement OLE.  
  
3.  Inscrire l'application avec OLE.  
  
4.  Créez un objet `COleTemplateServer` en tant que membre de la classe d'application.  
  
5.  Dans la fonction membre `InitInstance` de la classe d'application, procédez comme suit :  
  
    -   Connectez votre objet `COleTemplateServer` à vos modèles de document en appelant la fonction membre `ConnectTemplate` de l'objet.  
  
    -   Appelez la fonction membre du **COleTemplateServer::RegisterAll** pour enregistrer tous les objets de classe avec le système OLE.  
  
    -   Appelez `COleTemplateServer::UpdateRegistry`.  Le seul paramètre à `UpdateRegistry` doit être `OAT_CONTAINER` si l'application n'est pas ouverte avec le commutateur « \/Embedded ».  Cela enregistre l'application en tant que conteneur capable de prendre en charge les liens vers des objets incorporés.  
  
         Si l'application est ouverte avec le commutateur « \/Embedded », elle ne doit pas afficher la fenêtre principale, comme une application serveur.  
  
 L'exemple de liaison et incorporation d'objets MFC [OCLIENT](../top/visual-cpp-samples.md) implémente cette fonctionnalité.  Pour consulter un exemple montrant comment cela, consultez la fonction `InitInstance` dans le fichier d'OCLIENT.CPP de cet exemple d'application.  
  
## Voir aussi  
 [Conteneurs](../mfc/containers.md)   
 [Serveurs](../mfc/servers.md)