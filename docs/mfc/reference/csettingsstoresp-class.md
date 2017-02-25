---
title: "CSettingsStoreSP Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSettingsStoreSP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSettingsStoreSP class"
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CSettingsStoreSP Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CSettingsStoreSP` est une classe d'assistance que vous pouvez utiliser pour créer des instances de [CSettingsStore Class](../../mfc/reference/csettingsstore-class.md).  
  
## Syntaxe  
  
```  
class CSettingsStoreSP  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSettingsStoreSP::CSettingsStoreSP](../Topic/CSettingsStoreSP::CSettingsStoreSP.md)|Construit un objet `CSettingsStoreSP`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSettingsStoreSP::Create](../Topic/CSettingsStoreSP::Create.md)|Crée une instance d'une classe dérivée d' `CSettingsStore`.|  
|[CSettingsStoreSP::SetRuntimeClass](../Topic/CSettingsStoreSP::SetRuntimeClass.md)|Définit la classe d'exécution.  La méthode d' `Create` utilise la classe d'exécution pour déterminer quelle classe des objets à les créer.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|`m_dwUserData`|Données utilisateur personnalisées stockées dans l'objet d' `CSettingsStoreSP` .  Vous fournissez ces données dans le constructeur de l'objet d' `CSettingsStoreSP` .|  
|`m_pRegistry`|`CSettingsStore`objet dérivé que la méthode d' `Create` crée.|  
  
## Notes  
 Vous pouvez utiliser la classe d' `CSettingsStoreSP` pour rediriger toutes les opérations de Registre MFC à d'autres emplacements, tels qu'un fichier XML ou une base de données.  Pour cela, procédez comme suit :  
  
1.  Créez une classe \(telle qu' `CMyStore`\) et la dérivez\- d' `CSettingsStore`.  
  
2.  Utilisez les macros de [DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md) et d' [IMPLEMENT\_DYNCREATE](../Topic/IMPLEMENT_DYNCREATE.md) avec votre classe personnalisée d' `CSettingsStore` pour permettre la création dynamique.  
  
3.  Substituer les fonctions virtuelles et implémentez `Read` et `Write` s'exécute dans votre classe personnalisée.  Implémentez toute autre fonctionnalité pour lire et écrire des données à l'emplacement souhaité.  
  
4.  Dans votre application, appelez `CSettingsStoreSP::SetRuntimeClass` et passez un pointeur à [CRuntimeClass Structure](../../mfc/reference/cruntimeclass-structure.md) obtenu à partir de votre classe.  
  
 Chaque fois que l'infrastructure accéderait en général au Registre, il instanciera maintenant dynamiquement votre classe personnalisée et l'utilisera pour lire ou écrire des données.  
  
 `CSettingsStoreSP::SetRuntimeClass` utilise une variable statique globale.  Par conséquent, seule une mémoire personnalisée est disponible à la fois.  
  
## Configuration requise  
 **en\-tête :** afxsettingsstore.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CSettingsStore Class](../../mfc/reference/csettingsstore-class.md)