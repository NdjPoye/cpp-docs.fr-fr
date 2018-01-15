---
title: Clients Automation | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- clients, Automation
- Automation clients
- type libraries, Automation clients
- clients
ms.assetid: 84e34a79-06f6-4752-a33b-ae0ede1d8ecf
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9cfb6aae5c947d1f36019e548c72b22a3304aa12
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="automation-clients"></a>Clients Automation
L'Automation rend possible pour votre application la manipulation d'objets implémentés dans une autre application, ou l'exposition d'objets pour qu'ils puissent être manipulés. Un client Automation est une application qui peut manipuler des objets exposés appartenant à une autre application. L’application qui expose les objets est appelée serveur Automation. Le client manipule les objets de l’application serveur en accédant aux propriétés et fonctions de ces objets.  
  
### <a name="types-of-automation-clients"></a>Types de Clients Automation  
 Il existe deux types de clients Automation :  
  
-   Clients qui dynamiquement (au moment de l’exécution), obtiennent des informations sur les propriétés et les opérations du serveur.  
  
-   Clients qui possèdent des informations statiques (fournies au moment de la compilation) qui spécifie les propriétés et les opérations du serveur.  
  
 Les clients du premier type acquièrent des informations sur les méthodes et les propriétés du serveur en interrogeant le système OLE `IDispatch` mécanisme. Bien qu’il soit suffisante pour utiliser des clients dynamiques, `IDispatch` est difficile à utiliser pour les clients statiques, où les objets qui est contrôlée doit être connu au moment de la compilation. Pour les clients statiques, Microsoft Foundation classes fournissent la [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md) classe.  
  
 Clients avec liaison statique utilisent une classe proxy qui est liée de manière statique avec l’application cliente. Cette classe fournit une encapsulation C++ de type sécurisé de propriétés et les opérations de l’application serveur.  
  
 La classe `COleDispatchDriver` fournit la prise en charge principale pour le côté client d’Automation. À l’aide de la `Add New Item` boîte de dialogue, vous créez une classe dérivée de `COleDispatchDriver`.  
  
 Vous spécifiez ensuite le fichier de bibliothèque de types décrivant les propriétés et les fonctions de l’objet de l’application serveur. La boîte de dialogue Ajouter un élément lit ce fichier et crée le `COleDispatchDriver`-classe dérivée, avec des fonctions de membre que votre application peut appeler pour accéder aux objets de l’application serveur en C++ de manière sécurisée. Héritent de fonctionnalités supplémentaires `COleDispatchDriver` simplifie le processus d’appel le serveur Automation adéquat.  
  
### <a name="handling-events-in-automation-clients"></a>La gestion des événements dans les Clients Automation  
 Si vous souhaitez gérer des événements dans votre client automation, vous devez ajouter une interface du récepteur. MFC fournit la prise en charge de l’Assistant pour ajouter des interfaces de récepteur pour les contrôles ActiveX, mais pas en charge pour les autres serveurs COM. Pour plus d’informations sur l’ajout d’une interface du récepteur dans un client MFC pour les interfaces sources décrite par les serveurs COM, consultez Comment : créer une Interface du récepteur dans MFC COM Client (181845 Ko) à [http://support.microsoft.com/default.aspxscid=kb;en-us; 181845](http://support.microsoft.com/default.aspxscid=kb;en-us;181845).  
  
## <a name="see-also"></a>Voir aussi  
 [Clients Automation : Utilisation des bibliothèques de types](../mfc/automation-clients-using-type-libraries.md)   
 [Automation](../mfc/automation.md)   
 [Assistant Application MFC](../mfc/reference/mfc-application-wizard.md)

