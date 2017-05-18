---
title: "Prise en charge de Document, Assistant Application MFC composés | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.exe.compdoc
dev_langs:
- C++
ms.assetid: 42e1af83-12c4-438d-92eb-13835afdb148
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: e322824bd2887b50d72221cee67e2ba5cc46f2ea
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="compound-document-support-mfc-application-wizard"></a>Prise en charge des documents composés, Assistant Application MFC
Dans cette page de l’Assistant Application MFC, indiquer à quel niveau de votre application fournit une prise en charge des documents composés et actifs. Votre application doit prendre en charge l’architecture document/vue pour prendre en charge des documents composés et les modèles de document.  
  
 Par défaut, l’application ne contient aucune prise en charge des documents composés. Si vous acceptez cette valeur par défaut, votre application ne peut pas prendre en charge les documents actifs ou les fichiers composés.  
  
 **Prise en charge des documents composés**  
 Détermine si votre application fournit la prise en charge du conteneur, prise en charge du serveur ou les deux. Pour plus d’informations sur cette zone, consultez :  
  
-   [Conteneurs : Implémentation d’un conteneur](../../mfc/containers-implementing-a-container.md)  
  
-   [Serveurs : Implémentation d’un serveur](../../mfc/servers-implementing-a-server.md)  
  
|Option|Description|  
|------------|-----------------|  
|**Aucun**|N’indique aucune prise en charge pour la liaison et incorporation d’objets (OLE). Par défaut, l’Assistant application crée une application sans prise en charge ActiveX.|  
|**Conteneur**|Contient des objets liés et incorporés.|  
|**Mini-serveur**|Indique l’application peut créer et gérer des objets de document composé. Notez que les serveurs-mini ne peut pas exécuter en mode autonome et prennent uniquement en charge les éléments incorporés.|  
|**Serveur complet**|Indique l’application peut créer et gérer des objets de document composé. Serveurs complets sont en mesure d’exécuter en mode autonome et la prise en charge les éléments liés et incorporés.|  
|**Conteneur/serveur complet**|Indique que l’application peut être un conteneur et un serveur. Un conteneur est une application qui peut incorporer des éléments liés ou incorporés dans ses propres documents. Un serveur est une application qui peut créer des éléments Automation pour une utilisation par les applications conteneurs.|  
  
 **Options supplémentaires**  
 Indique si votre application prend en charge les documents actifs. Consultez la page [Documents actifs](../../mfc/active-documents.md) pour plus d’informations sur cette fonctionnalité.  
  
|Option|Description|  
|------------|-----------------|  
|**Serveur de documents actifs**|Indique l’application peut créer et gérer des documents actifs. Si vous sélectionnez cette option, vous devez spécifier une extension de fichier pour votre serveur de documents actifs dans le **l’extension de fichier** zone le [chaînes modèles de Document](../../mfc/reference/document-template-strings-mfc-application-wizard.md) page de l’Assistant. Consultez la page [serveurs de documents actifs](../../mfc/active-document-servers.md) pour plus d’informations.|  
|**Conteneur de documents actifs**|Indique que l’application peut contenir des documents actifs dans son frame. Les documents actifs peuvent inclure, par exemple, des documents Internet Explorer ou des documents Office tels que des fichiers Microsoft Word ou des feuilles de calcul Excel. Consultez la page [relation contenant-contenu de Document actif](../../mfc/active-document-containment.md) pour plus d’informations.|  
|**Prise en charge des fichiers composés**|Ne sérialise pas les documents de l’application conteneur en utilisant le format de fichier composé. Cette option force le chargement d’un fichier entier contenant des objets en mémoire. Les sauvegardes incrémentielles à des objets individuels ne sont pas disponibles. Si un objet est modifié et enregistré par la suite, tous les objets dans le fichier sont enregistrés.|  
  
## <a name="see-also"></a>Voir aussi  
 [Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md)


