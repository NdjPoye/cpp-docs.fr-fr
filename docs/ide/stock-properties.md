---
title: "Propri&#233;t&#233;s stock | Microsoft Docs"
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
  - "propriétés stock"
  - "propriétés stock, à propos des propriétés stock"
ms.assetid: a89fc454-0b8e-447a-9033-4c8af46a24d9
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Propri&#233;t&#233;s stock
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vous ajoutez une propriété à une dispinterface MFC à l'aide de l'[Assistant Ajout de propriété](../ide/idl-attributes-add-property-wizard.md), vous pouvez choisir une propriété stock dans la liste **Nom de la propriété** de la page [Noms](../ide/names-add-property-wizard.md) de l'Assistant.  Ces propriétés sont les suivantes :  
  
|Nom de la propriété|Description|  
|-------------------------|-----------------|  
|**Apparence**|Retourne ou définit une valeur indiquant l'apparence du contrôle.  La propriété **Appearance** du contrôle peut inclure ou omettre les effets d'affichage à trois dimensions.  Il s'agit d'une propriété ambiante en lecture\/écriture.|  
|`BackColor`|Retourne ou définit la propriété `BackColor` ambiante du contrôle à une couleur de la palette \(RGB\) ou à une couleur système prédéfinie.  Par défaut, sa valeur correspond à la couleur de premier plan du conteneur du contrôle.  Il s'agit d'une propriété ambiante en lecture\/écriture.|  
|`BorderStyle`|Retourne ou définit le style de la bordure d'un contrôle.  Cette propriété est en lecture\/écriture.|  
|**Caption**|Retourne ou définit la propriété **Caption** du contrôle.  La légende est le titre de la fenêtre.  **Caption** n'a pas de type d'implémentation **Variable membre**.|  
|**Activé**|Retourne ou définit la propriété **Enabled** du contrôle.  Un contrôle activé peut répondre aux événements générés par l'utilisateur.|  
|**Police**|Retourne ou définit la police ambiante du contrôle.  Retourne ou définit la valeur Null si le contrôle n'a pas de police.|  
|`ForeColor`|Retourne ou définit la propriété `ForeColor` ambiante du contrôle.|  
|**hWnd**|Retourne ou définit la propriété **hWnd** du contrôle.  **hWnd** n'a aucun type d'implémentation **Variable membre**.|  
|**ReadyState**|Retourne ou définit la propriété **ReadyState** du contrôle.  Un contrôle peut être non initialisé, initialisé, en chargement, interactif ou complet.  Pour plus d'informations, consultez [READYSTATE](https://msdn.microsoft.com/en-us/library/aa768362.aspx) dans le *Kit de développement Internet SDK*.|  
|**Texte**|Retourne ou définit le texte contenu dans un contrôle.  **Text** n'a pas de type d'implémentation **Variable membre**.|  
  
## Voir aussi  
 [Ajout d'une propriété](../ide/adding-a-property-visual-cpp.md)   
 [Attributs IDL, Assistant Ajout de propriété](../ide/idl-attributes-add-property-wizard.md)