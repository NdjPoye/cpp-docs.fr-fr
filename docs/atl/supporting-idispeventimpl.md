---
title: "Supporting IDispEventImpl | Microsoft Docs"
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
  - "IDispEventImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, IDispEventImpl support in COM objects"
  - "BEGIN_SINK_MAP macro"
  - "event sink maps, déclarer"
  - "IDispEventImpl class, advising and unadvising"
  - "IDispEventImpl class, déclarer"
  - "SINK_ENTRY macro"
  - "bibliothèques de types, importer"
ms.assetid: b957f930-6a5b-4598-8e4d-8027759957e7
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Supporting IDispEventImpl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle [IDispEventImpl](../atl/reference/idispeventimpl-class.md) peut être utilisée pour fournir la prise en charge des récepteurs de point de connexion dans votre classe ATL.  Un récepteur de point de connexion permet à votre classe pour gérer des événements déclenchés des objets COM externes.  Les récepteurs de point de connexion sont mappés à une table de récepteurs d'événements, fournies par la classe.  
  
 Pour implémenter correctement un récepteur de point de connexion pour votre classe, les étapes suivantes doivent être effectuées :  
  
-   Importez les bibliothèques de types pour chaque objet externe  
  
-   Déclarez les interfaces d' `IDispEventImpl`  
  
-   Déclarez une table de récepteurs d'événements  
  
-   Avertit et unadvise les points de connexion  
  
 Les étapes en implémentant un récepteur de tout point de connexion sont accomplies en modifiant que le fichier d'en\-tête \(.h\) de votre classe.  
  
## Importer des bibliothèques de types  
 Pour chaque objet externe dont les événements à gérer, vous devez importer la bibliothèque de types.  Cette étape définit des événements qui peuvent être gérés et fournit des informations qui sont utilisées en déclarant la table de récepteurs d'événements.  La directive de [\#import](../preprocessor/hash-import-directive-cpp.md) peut être utilisée pour ce faire.  Ajoutez les lignes directives nécessaires pour `#import` pour chaque interface de dispatch que vous supporterez au fichier d'en\-tête \(.h\) de votre classe.  
  
 L'exemple suivant importe la bibliothèque de types à partir d'un serveur COM externe \(`MSCAL.Calendar.7`\) :  
  
 [!code-cpp[NVC_ATL_Windowing#141](../atl/codesnippet/CPP/supporting-idispeventimpl_1.h)]  
  
> [!NOTE]
>  Vous devez avoir une instruction distincte d' `#import` pour chaque bibliothèque de types externe que vous supporterez.  
  
## Déclarer les interfaces d'IDispEventImpl  
 Maintenant que vous avez importé les bibliothèques de types de chaque interface de dispatch, vous devez déclarer les interfaces distinctes d' `IDispEventImpl` pour chaque interface de dispatch externe.  Modifiez la déclaration de la classe en ajoutant une déclaration d'interface d' `IDispEventImpl` pour chaque objet externe.  Pour plus d'informations sur les paramètres, consultez l' [IDispEventImpl](../atl/reference/idispeventimpl-class.md).  
  
 Le code suivant déclare deux récepteurs de point de connexion, pour l'interface d' `DCalendarEvents` , car l'objet COM implémenté par la classe `CMyCompositCtrl2`:  
  
 [!code-cpp[NVC_ATL_Windowing#142](../atl/codesnippet/CPP/supporting-idispeventimpl_2.h)]  
  
## Déclarer une table de récepteurs d'événements  
 Pour que les notifications d'événements soient gérées par la fonction RFX, votre classe doit router chaque événement à son gestionnaire approprié.  Cela est accompli en déclarant une table de récepteurs d'événements.  
  
 ATL fournit plusieurs macros, [BEGIN\_SINK\_MAP](../Topic/BEGIN_SINK_MAP.md), [END\_SINK\_MAP](../Topic/END_SINK_MAP.md), et [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY.md), qui facilitent ce mappage.  Le format standard est la suivante :  
  
 `BEGIN_SINK_MAP(comClass)`  
  
 `SINK_ENTRY_EX(id, iid, dispid, func)`  
  
 `.  .  .  //additional external event entries`  
  
 `END_SINK_MAP()`  
  
 L'exemple suivant déclare une table de récepteurs d'événements avec deux gestionnaires d'événements :  
  
 [!code-cpp[NVC_ATL_Windowing#136](../atl/codesnippet/CPP/supporting-idispeventimpl_3.h)]  
  
 L'implémentation est presque complète.  La dernière étape concerne notifier et unadvising des interfaces externes.  
  
## Notifier et Unadvising les interfaces d'IDispEventImpl  
 La dernière étape consiste à implémenter une méthode qui avertit \(ou\) unadvise tous les points de connexion aux temps appropriés.  Cette opération qui signale doit être effectué avant communication entre les clients externes et votre objet peut avoir lieu.  Avant que votre objet soit visible, chaque interface de dispatch externe prise en charge par votre objet est interrogé pour les interfaces sortantes.  Une connexion établie et une référence à l'interface sortante est utilisée pour gérer des événements de l'objet.  Cette procédure sous le nom « informant ».  
  
 Une fois que votre objet soit terminé avec les interfaces externes, il doit annoncer les interfaces sortantes qu'elles ne sont plus utilisées par votre classe.  Ce processus sous le nom « unadvising ».  
  
 En raison de la seule nature des objets COM, cette procédure varie, en détail et exécution, entre les implémentations.  Ces informations sont le cadre de cette rubrique et ne sont pas adressés.  
  
## Voir aussi  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)