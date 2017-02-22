---
title: "CSettingsStore Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSettingsStore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSettingsStore class"
ms.assetid: 0ea181de-a13e-4b29-b560-7c43838223ff
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# CSettingsStore Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule les fonctions API Windows, fournissant une interface orientée objet que vous utilisez pour accéder au Registre.  
  
## Syntaxe  
  
```  
class CSettingsStore : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSettingsStore::CSettingsStore](../Topic/CSettingsStore::CSettingsStore.md)|Construit un objet `CSettingsStore`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSettingsStore::Close](../Topic/CSettingsStore::Close.md)|Ferme la clé de Registre ouverte.|  
|[CSettingsStore::CreateKey](../Topic/CSettingsStore::CreateKey.md)|Ouvre la clé spécifiée ou la crée si elle n'existe pas.|  
|[CSettingsStore::DeleteKey](../Topic/CSettingsStore::DeleteKey.md)|Supprime la clé spécifiée et tous ses enfants.|  
|[CSettingsStore::DeleteValue](../Topic/CSettingsStore::DeleteValue.md)|Supprime la valeur spécifiée de la clé ouverte.|  
|[CSettingsStore::Open](../Topic/CSettingsStore::Open.md)|Ouvre la clé spécifiée.|  
|[CSettingsStore::Read](../Topic/CSettingsStore::Read.md)|Récupère les données d'une valeur de clé spécifiée.|  
|[CSettingsStore::Write](../Topic/CSettingsStore::Write.md)|Écrit une valeur au Registre sous la clé ouverte.|  
  
## Notes  
 Les fonctions membres `CreateKey` et `Open` sont très similaires.  Si la clé de Registre existe déjà, `CreateKey` et fonction d' `Open` de la même façon.  Toutefois, si la clé de Registre n'existe pas, `CreateKey` la crée alors qu' `Open` retourne une valeur d'erreur.  
  
## Exemple  
 L'exemple suivant montre comment utiliser l'ouvrir et lire des méthodes de classe d' `CSettingsStore` .  Cet extrait de code fait partie d' [Exemple de démonstration d'Info\-bulle](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_ToolTipDemo#1](../../mfc/reference/codesnippet/CPP/csettingsstore-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSettingsStore](../../mfc/reference/csettingsstore-class.md)  
  
## Configuration requise  
 **en\-tête :** afxsettingsstore.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)