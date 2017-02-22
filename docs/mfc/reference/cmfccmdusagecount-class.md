---
title: "CMFCCmdUsageCount Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCCmdUsageCount"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCCmdUsageCount class"
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CMFCCmdUsageCount Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Suit le nombre d'utilisation de messages windows, lorsque l'utilisateur sélectionne un élément d'un menu.  
  
## Syntaxe  
  
```  
class CMFCCmdUsageCount : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|Constructeur par défaut.|  
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|Destructor.|  
  
### Méthodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCCmdUsageCount::AddCmd](../Topic/CMFCCmdUsageCount::AddCmd.md)|Un index par le compteur associé à la commande donnée.|  
|[CMFCCmdUsageCount::GetCount](../Topic/CMFCCmdUsageCount::GetCount.md)|Récupère le nombre d'aide associé à l'ID donnée de commande|  
|[CMFCCmdUsageCount::HasEnoughInformation](../Topic/CMFCCmdUsageCount::HasEnoughInformation.md)|Détermine si cet objet collecté la quantité minimale de données de suivi.|  
|[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](../Topic/CMFCCmdUsageCount::IsFreqeuntlyUsedCmd.md)|Détermine si la commande donnée est fréquemment utilisée.|  
|[CMFCCmdUsageCount::Reset](../Topic/CMFCCmdUsageCount::Reset.md)|Efface le nombre d'utilisation de toutes les commandes.|  
|[CMFCCmdUsageCount::Serialize](../Topic/CMFCCmdUsageCount::Serialize.md)|Lit cet objet d'une archive ou l'écrit dans une archive.  \(Substitutions [CObject::Serialize](../Topic/CObject::Serialize.md).\)|  
|[CMFCCmdUsageCount::SetOptions](../Topic/CMFCCmdUsageCount::SetOptions.md)|Définit les valeurs des données membres des classes partagées d' `CMFCCmdUsageCount` .|  
  
### Membres de données  
  
|||  
|-|-|  
|Nom|Description|  
|`m_CmdUsage`|Un objet d' `CMap` qui mappe des commandes à leur utilisation compte.|  
|`m_nMinUsagePercentage`|Le pourcentage minimum d'utilisation pour une commande est fréquemment utilisée.|  
|`m_nStartCount`|Le compteur de début utilisé pour déterminer si cet objet collecté la quantité minimale de données de suivi.|  
|`m_nTotalUsage`|Le nombre de toutes les commandes dessinées.|  
  
### Remarques  
 La classe d' `CMFCCmdUsageCount` mappe chaque identificateur de message numérique windows à un compteur d'entier non signé 32 bits.  `CMFCToolBar` utilise cette classe pour afficher les éléments fréquemment utilisés de barre d'outils.  Pour plus d'informations sur `CMFCToolBar`, consultez [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md).  
  
 Vous pouvez rendre des données de classe d' `CMFCCmdUsageCount` entre l'exécution de votre programme.  Utilisez la méthode de [CMFCCmdUsageCount::Serialize](../Topic/CMFCCmdUsageCount::Serialize.md) pour sérialiser des données membres de classe et la méthode de [CMFCCmdUsageCount::SetOptions](../Topic/CMFCCmdUsageCount::SetOptions.md) pour placer les données membres partagés.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)  
  
## Configuration requise  
 **en\-tête :** afxcmdusagecount.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)