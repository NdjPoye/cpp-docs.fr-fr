---
title: "ASP, Assistant Composant ASP ATL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.asp.asp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Composant ASP ATL, ASP"
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ASP, Assistant Composant ASP ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez la page ASP de l'Assistant Composant Active Server Page ATL pour spécifier des paramètres facultatifs permettant de gérer les informations et l'état concernant le composant ASP.  
  
 **Méthodes facultatives**  
 Ajoute les méthodes ASP facultatives **OnStartPage** et **OnEndPage** à votre objet.  Cette option doit être sélectionnée pour pouvoir définir des objets intrinsèques Active Server Pages.  Elle est sélectionnée par défaut.  
  
-   **OnStartPage\/OnEndPage** [OnStartPage](https://msdn.microsoft.com/en-us/library/ms691624.aspx) est appelé la première fois que le script essaie d'accéder à l'objet.  La méthode **OnEndPage** est appelée lorsque l'objet a terminé le traitement du script.  
  
 **Objets intrinsèques**  
 Vous devez sélectionner l'option **OnStartPage\/OnEndPage** pour pouvoir définir des objets intrinsèques ASP.  
  
|Option|Description|  
|------------|-----------------|  
|**Requête**|Permet d'accéder à l'objet **Request** intrinsèque Active Server Pages.  L'objet Request est utilisé pour passer une demande HTTP.|  
|**Réponse**|Permet d'accéder à l'objet **Response** intrinsèque Active Server Pages.  En réponse à une demande, l'objet Response envoie au navigateur des informations à afficher à l'écran de l'utilisateur.|  
|**Session**|Permet d'accéder à l'objet **Session** intrinsèque Active Server Pages.  L'objet **Session** conserve les informations concernant la session utilisateur en cours, en procédant notamment au stockage et à l'extraction des informations d'état.|  
|**Application**|Permet d'accéder à l'objet **Application** intrinsèque Active Server Pages.  L'objet **Application** gère l'état partagé entre plusieurs objets ASP.|  
|**Serveur**|Permet d'accéder à l'objet **Server** intrinsèque Active Server Pages.  L'objet **Server** vous permet de créer d'autres objets ASP.|  
  
## Voir aussi  
 [Composant Active Server Page ATL \(Assistant\)](../../atl/reference/atl-active-server-page-component-wizard.md)   
 [ATL Active Server Page Component](../../atl/reference/adding-an-atl-active-server-page-component.md)