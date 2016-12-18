---
title: "Prise en charge des documents compos&#233;s, Assistant Application MFC | Microsoft Docs"
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
  - "vc.appwiz.mfc.exe.compdoc"
dev_langs: 
  - "C++"
ms.assetid: 42e1af83-12c4-438d-92eb-13835afdb148
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Prise en charge des documents compos&#233;s, Assistant Application MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dans la page Prise en charge des documents composés de l'Assistant Application MFC, indiquez le niveau de prise en charge fourni par votre application pour les documents composés et actifs.  Votre application doit prendre en charge l'architecture Document\/Vue pour pouvoir prendre en charge les documents composés et les modèles de document.  
  
 Par défaut, l'application n'intègre aucune prise en charge des documents composés.  Si vous acceptez la valeur par défaut, votre application ne peut pas prendre en charge les documents actifs ou les fichiers composés.  
  
 **Prise en charge des documents composés**  
 Détermine si votre application assure une prise en charge du conteneur, du serveur, ou les deux.  Pour plus d'informations sur ces points, consultez :  
  
-   [Conteneurs : implémentation d'un conteneur](../../mfc/containers-implementing-a-container.md)  
  
-   [Serveurs : implémentation d'un serveur](../../mfc/servers-implementing-a-server.md)  
  
|Option|Description|  
|------------|-----------------|  
|**None**|Indique que la liaison et l'incorporation d'objets \(OLE, Object Linking and Embedding\) ne sont pas prises en charge.  Par défaut, l'Assistant Application crée une application dépourvue de prise en charge ActiveX.|  
|**Conteneur**|Contient des objets liés et incorporés.|  
|**Mini\-serveur**|Indique que l'application peut créer et gérer des objets de document composé.  Notez que les mini\-serveurs ne peuvent pas être exécutés en mode autonome et qu'ils prennent en charge uniquement les éléments incorporés.|  
|**Serveur complet**|Indique que l'application peut créer et gérer des objets de document composé.  Les serveurs complets peuvent être exécutés en mode autonome et ils prennent en charge les éléments liés et incorporés.|  
|**Conteneur\/Serveur complet**|Indique que l'application peut être à la fois un conteneur et un serveur.  Un conteneur est une application qui peut incorporer des éléments liés ou incorporés dans ses propres documents.  Un serveur est une application qui peut créer des éléments Automation pour une utilisation par les applications conteneurs.|  
  
 **Options supplémentaires**  
 Indique si votre application prend en charge les documents actifs.  Consultez [Documents actifs](../../mfc/active-documents.md) pour plus d'informations sur cette fonctionnalité.  
  
|Option|Description|  
|------------|-----------------|  
|**Serveur de documents actifs**|Indique que l'application peut créer et gérer des documents actifs.  Si vous sélectionnez cette option, vous devez spécifier une extension de fichier pour le serveur de documents actifs dans la zone **Extension de fichier** de la page [Chaînes modèles de document](../../mfc/reference/document-template-strings-mfc-application-wizard.md) de l'Assistant.  Pour plus d'informations, consultez [Serveurs de documents actifs](../../mfc/active-document-servers.md).|  
|**Conteneur de documents actifs**|Indique que l'application peut contenir des documents actifs dans son frame.  Les documents actifs peuvent par exemple inclure des documents Internet Explorer ou des documents Office comme des fichiers Microsoft Word ou des feuilles de calcul Excel.  Pour plus d'informations, consultez [Relation contenant\-contenu de document actif](../../mfc/active-document-containment.md).|  
|**Prise en charge des fichiers composés**|Ne sérialise pas les documents de l'application conteneur à l'aide du format de fichier composé.  Cette option force le chargement en mémoire d'un fichier entier contenant les objets.  Les enregistrements incrémentiels d'objets individuels ne sont pas disponibles.  Si un objet est modifié, puis enregistré par la suite, tous les objets contenus dans le fichier sont enregistrés.|  
  
## Voir aussi  
 [Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md)