---
title: "Ajout d’un consommateur ATL OLE DB | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding ATL OLE DB consumers
- OLE DB, adding ATL OLE DB consumer to projects
- ATL OLE DB consumers
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
caps.latest.revision: 11
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c7202444e1b3aa473060df359dbeb8a8668f65f4
ms.lasthandoff: 02/24/2017

---
# <a name="adding-an-atl-ole-db-consumer"></a>Ajout d’un consommateur ATL OLE DB
Utilisez cet Assistant pour ajouter un consommateur OLE DB ATL à un projet. Un consommateur OLE DB ATL se compose d’une OLE DB accesseur classe et les données des liaisons nécessaires pour accéder à une source de données. Le projet doit avoir été créé comme une application ATL COM ou comme une application MFC ou Win32 qui contient la prise en charge ATL (que l’Assistant Consommateur OLE DB ATL ajoute automatiquement).  
  
 **Remarque** vous pouvez ajouter un consommateur OLE DB à un projet MFC. Si vous le faites, l’Assistant Consommateur OLE DB ATL ajoute la prise en charge COM nécessaire à votre projet. Cela suppose que lorsque vous avez créé le projet MFC, vous avez sélectionné le **contrôles ActiveX** case (dans le **fonctionnalités avancées** page de l’Assistant Application MFC), qui est activé par défaut. Cette option garantit que l’application appelle **CoInitialize** et **CoUninitialize**. Si vous n’avez pas sélectionné **contrôles ActiveX** lorsque vous avez créé le projet MFC, vous devez appeler **CoInitialize** et **CoUninitialize** dans votre code principal.  
  
### <a name="to-add-an-atl-ole-db-consumer-to-your-project"></a>Pour ajouter un consommateur OLE DB ATL à votre projet  
  
1.  Dans l’affichage de classes, cliquez sur le projet. Dans le menu contextuel, cliquez sur **ajouter** , puis **ajouter une classe**.  
  
2.  Dans le dossier Visual C++, double-cliquez sur le **consommateur OLE DB ATL** icône ou sélectionnez-la et cliquez sur **ouvrir**.  
  
     L’Assistant Consommateur OLE DB ATL s’ouvre.  
  
3.  Définissez les paramètres comme décrit dans [Assistant Consommateur OLE DB ATL](../../atl/reference/atl-ole-db-consumer-wizard.md).  
  
4.  Cliquez sur **Terminer** pour fermer l’Assistant. Le code du consommateur OLE DB nouvellement créé sera inséré dans votre projet.  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout de fonctionnalités à l’aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)


