---
title: "Proc&#233;dure pas &#224; pas&#160;: cr&#233;ation d&#39;un bloc de message personnalis&#233; | Microsoft Docs"
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
  - "créer des blocs de messages personnalisés (runtime d'accès concurrentiel)"
  - "blocs de messages personnalisés, créer (Runtime d’accès concurrentiel)"
ms.assetid: 4c6477ad-613c-4cac-8e94-2c9e63cd43a1
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: cr&#233;ation d&#39;un bloc de message personnalis&#233;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce document décrit comment créer un type de bloc de message personnalisé qui classe les messages entrants par priorité.  
  
 Bien que les types de blocs de messages intégrés fournissent un large éventail de fonctionnalités, vous pouvez créer votre propre type de bloc de message et le personnaliser pour répondre aux exigences de votre application. Pour obtenir une description des types de bloc de messages intégrés fournis par la bibliothèque d’Agents asynchrones, consultez la page [des blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="prerequisites"></a>Prérequis  
 Lisez les documents suivants avant de commencer cette procédure pas à pas :  
  
- [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)  
  
- [Fonctions de passage de message](../../parallel/concrt/message-passing-functions.md)  
  
##  <a name="a-nametopa-sections"></a><a name="top"></a> Sections  
 Cette procédure pas à pas contient les sections suivantes :  
  
- [Conception d’un bloc de Message personnalisé](#design)  
  
- [Définition de la classe priority_buffer](#class)  
  
- [L’exemple complet](#complete)  
  
##  <a name="a-namedesigna-designing-a-custom-message-block"></a><a name="design"></a> Conception d’un bloc de Message personnalisé  
 Blocs de messages participent consistant à envoyer et recevoir des messages. Un bloc de message qui envoie des messages est appelé un *bloc source*. Un bloc de message qui reçoit des messages est appelé un *bloc cible*. Un bloc de message qui envoie et reçoit des messages est appelé un *bloc propagateur*. La bibliothèque d’Agents utilise la classe abstraite [concurrency::ISource](../../parallel/concrt/reference/isource-class.md) pour représenter des blocs sources et la classe abstraite [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md) pour représenter des blocs cibles. Les types de blocs de message qui agissent comme sources dérivent `ISource`; les types de blocs de message qui agissent comme cibles dérivent `ITarget`.  
  
 Bien que vous pouvez dériver votre type de bloc de message directement à partir de `ISource` et `ITarget`, la bibliothèque d’Agents définit trois classes de base qui effectuent la plupart des fonctionnalités communes à tous les types de bloc de message, par exemple, la gestion des erreurs et messages de connexion de blocs de manière concurrentiel. Le [concurrency::source_block](../../parallel/concrt/reference/source-block-class.md) dérive de la classe `ISource` et envoie des messages à d’autres blocs. Le [concurrency::target_block](../../parallel/concrt/reference/target-block-class.md) dérive de la classe `ITarget` et reçoit des messages d’autres blocs. Le [concurrency::propagator_block](../../parallel/concrt/reference/propagator-block-class.md) dérive de la classe `ISource` et `ITarget` et envoie des messages à d’autres blocs et il reçoit des messages d’autres blocs. Nous vous recommandons d’utiliser ces trois classes de base pour gérer les détails de l’infrastructure afin que vous pouvez vous concentrer sur le comportement de votre bloc de message.  
  
 Le `source_block`, `target_block`, et `propagator_block` classes sont des modèles qui sont paramétrables sur un type qui gère les connexions ou les liens entre les blocs sources et cibles et sur un type qui gère la façon dont les messages sont traités. La bibliothèque d’Agents définit deux types de lien gérer, [concurrency::single_link_registry](../../parallel/concrt/reference/single-link-registry-class.md) et [concurrency::multi_link_registry](../../parallel/concrt/reference/multi-link-registry-class.md). La `single_link_registry` classe permet à un bloc de message d’être lié à une source ou cible. La `multi_link_registry` classe permet à un bloc de message être lié à plusieurs sources ou cibles multiples. La bibliothèque d’Agents définit une classe qui assure la gestion du message, [concurrency::ordered_message_processor](../../parallel/concrt/reference/ordered-message-processor-class.md). La `ordered_message_processor` classe permet aux blocs de message traiter les messages dans l’ordre dans lequel il les reçoit.  
  
 Pour mieux comprendre les blocs de messages interaction avec leurs sources et les cibles, prenons l’exemple suivant. Cet exemple illustre la déclaration de la [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) classe.  
  
 [!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_1.cpp)]  
  
 Le `transformer` dérive de la classe `propagator_block`, et par conséquent sert à la fois un bloc source et un bloc cible. Il accepte des messages de type `_Input` et envoie des messages de type `_Output`. La `transformer` classe spécifie `single_link_registry` que le Gestionnaire de liaisons pour tous les blocs cibles et `multi_link_registry` en tant que le Gestionnaire de liaisons pour tous les blocs de code source. Par conséquent, un `transformer` objet peut contenir une cible et un nombre illimité de sources.  
  
 Une classe qui dérive de `source_block` doit implémenter six méthodes : [propagate_to_any_targets](../Topic/source_block::propagate_to_any_targets%20Method.md), [accept_message](../Topic/source_block::accept_message%20Method.md), [reserve_message](../Topic/source_block::reserve_message%20Method.md), [consume_message](../Topic/source_block::consume_message%20Method.md), [release_message](../Topic/source_block::release_message%20Method.md), et [resume_propagation](../Topic/source_block::resume_propagation%20Method.md). Une classe qui dérive de `target_block` doit implémenter le [propagate_message](../Topic/propagator_block::propagate_message%20Method.md) méthode et peut éventuellement implémenter la [send_message](../Topic/propagator_block::send_message%20Method.md) méthode. Dérivation de `propagator_block` est fonctionnellement équivalente à la dérivation à partir de deux `source_block` et `target_block`.  
  
 Le `propagate_to_any_targets` méthode est appelée par le runtime pour traiter tous les messages entrants et les propage les messages sortants en mode asynchrone ou synchrone. Le `accept_message` méthode est appelée par les blocs cibles pour recevoir des messages. Plusieurs types de blocs de messages telles que `unbounded_buffer`, envoyer des messages uniquement à la première cible qui les reçoit. Par conséquent, il transfère la propriété du message à la cible. Types d’autres blocs de messages, tels que [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md), envoient des messages à chacun de ses blocs cibles. Par conséquent, `overwrite_buffer` crée une copie du message pour chacune de ses cibles.  
  
 Le `reserve_message`, `consume_message`, `release_message`, et `resume_propagation` méthodes permettent de participer à la réservation de messages des blocs de messages. Cible bloque l’appel à la `reserve_message` méthode lorsqu’ils sont proposés à un message et que vous doivent réserver le message pour une utilisation ultérieure. Après un bloc cible réserve un message, elle peut appeler le `consume_message` méthode consommer ce message ou le `release_message` méthode pour annuler la réservation. Comme avec la `accept_message` (méthode), l’implémentation de `consume_message` peut transférer la propriété du message ou retourner une copie du message. Après un bloc cible consomme ou libère un message réservé, le runtime appelle le `resume_propagation` (méthode). En règle générale, cette méthode continue la propagation de messages, commençant par le message suivant dans la file d’attente.  
  
 Le runtime appelle la `propagate_message` méthode pour transférer de façon asynchrone un message à partir d’un autre bloc pour l’objet actuel. Le `send_message` méthode ressemble à `propagate_message`, sauf qu’elle, au lieu de façon asynchrone, envoie de façon synchrone le message aux blocs cibles. L’implémentation par défaut de `send_message` rejette tous les messages entrants. Le runtime n’appelle pas une de ces méthodes si le message ne passe pas la fonction de filtre facultative associée au bloc cible. Pour plus d’informations sur les filtres de messages, consultez la page [des blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md).  
  
 [[Haut](#top)]  
  
##  <a name="a-nameclassa-defining-the-prioritybuffer-class"></a><a name="class"></a> Définition de la classe priority_buffer  
 La `priority_buffer` classe est un type de bloc de message personnalisé qui classe les messages entrants par priorité, puis par l’ordre dans lequel ils sont reçus. Le `priority_buffer` ressemble à la [concurrency::unbounded_buffer](../Topic/unbounded_buffer%20Class.md) classe, car elle contient une file d’attente de messages et également parce qu’il agit comme une source et un bloc de message cible et peut avoir plusieurs sources et plusieurs cibles. Toutefois, `unbounded_buffer` bases propagation uniquement sur l’ordre dans lequel elle reçoit des messages de ses sources de message.  
  
 La `priority_buffer` classe reçoit des messages de type std ::[tuple](../../standard-library/tuple-class.md) contenant `PriorityType` et `Type` éléments. `PriorityType` fait référence au type qui contient la priorité de chaque message. `Type` fait référence à la partie données du message. La `priority_buffer` classe envoie des messages de type `Type`. La `priority_buffer` classe gère également deux files d’attente : un [std::priority_queue](../../standard-library/priority-queue-class.md) objet pour les messages entrants et un std ::[file d’attente](../../standard-library/queue-class.md) objet pour les messages sortants. Classer par priorité les messages est utile quand un `priority_buffer` objet reçoit simultanément plusieurs messages ou lorsqu’il reçoit des messages avant que les messages sont lus par les consommateurs.  
  
 Outre les sept méthodes qu’une classe qui dérive de `propagator_block` doit implémenter, la `priority_buffer` classe également substitue le `link_target_notification` et `send_message` méthodes. La `priority_buffer` classe définit également deux méthodes d’assistance publiques, `enqueue` et `dequeue`, et une méthode d’assistance privée, `propagate_priority_order`.  
  
 La procédure suivante décrit comment implémenter la `priority_buffer` classe.  
  
#### <a name="to-define-the-prioritybuffer-class"></a>Pour définir la classe priority_buffer  
  
1.  Créez un fichier d’en-tête C++ et nommez-le `priority_buffer.h`. Vous pouvez également utiliser un fichier d’en-tête existant qui fait partie de votre projet.  
  
2.  Dans `priority_buffer.h`, ajoutez le code suivant.  
  
 [!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_2.h)]  
  
3.  Dans la `std` espace de noms, définissez les spécialisations de [std::less](../../standard-library/less-struct.md) et [std::greater](../../standard-library/greater-struct.md) qui agissent sur la concurrence ::[message](../../parallel/concrt/reference/message-class.md) objets.  
  
 [!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_3.h)]  
  
     La `priority_buffer` classe magasins `message` des objets dans une `priority_queue` objet. Ces spécialisations de type permettent la file d’attente de priorité trier les messages selon leur priorité. La priorité est le premier élément de la `tuple` objet.  
  
4.  Dans la `concurrencyex` espace de noms, déclarez la `priority_buffer` classe.  
  
 [!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_4.h)]  
  
     La classe `priority_buffer` dérive de la classe `propagator_block`. Par conséquent, elle peut envoyer et recevoir des messages. La `priority_buffer` classe peut avoir plusieurs cibles qui reçoivent des messages de type `Type`. Il peut également comporter plusieurs sources qui envoient des messages de type `tuple<PriorityType, Type>`.  
  
5.  Dans la `private` section de la `priority_buffer` de classe, ajoutez les variables de membre suivantes.  
  
 [!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_5.h)]  
  
     Le `priority_queue` objet conserve les messages entrants ; le `queue` objet conserve les messages sortants. Un `priority_buffer` objet peut recevoir plusieurs messages simultanément ; le `critical_section` objet synchronise l’accès à la file d’attente de messages d’entrée.  
  
6.  Dans la `private` section, définissez le constructeur de copie et de l’opérateur d’assignation. Cela empêche `priority_queue` objets ne soient pas être assigné.  
  
 [!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_6.h)]  
  
7.  Dans la `public` section, définissez les constructeurs communs à de nombreux types de bloc de message. Définissez également le destructeur.  
  
 [!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_7.h)]  
  
8.  Dans la `public` section, définissez les méthodes `enqueue` et `dequeue`. Ces méthodes d’assistance fournissent un autre moyen d’envoyer des messages et recevoir des messages une `priority_buffer` objet.  
  
 [!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_8.h)]  
  
9. Dans la `protected` section, définissez la `propagate_to_any_targets` (méthode).  
  
 [!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_9.h)]  
  
     Le `propagate_to_any_targets` méthode transfère le message au début de la file d’attente d’entrée vers la file d’attente de sortie et propage tous les messages dans la file d’attente de sortie.  
  
10. Dans la `protected` section, définissez la `accept_message` (méthode).  
  
 [!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_10.h)]  
  
     Lorsqu’un bloc cible appelle la `accept_message` (méthode), la `priority_buffer` classe transfère la propriété du message au premier bloc cible qui le reçoit. (Cela ressemble à celui du `unbounded_buffer`.)  
  
11. Dans la `protected` section, définissez la `reserve_message` (méthode).  
  
 [!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_11.h)]  
  
     La `priority_buffer` classe autorise un bloc cible de réserver un message lorsque l’identificateur de message fourni correspond à l’identificateur du message qui se trouve au début de la file d’attente. En d’autres termes, une cible peut réserver le message si le `priority_buffer` objet n’a pas encore reçu un message supplémentaire et n’ont pas encore été propagées à l’objet actuel.  
  
12. Dans la `protected` section, définissez la `consume_message` (méthode).  
  
 [!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_12.h)]  
  
     Un bloc cible appelle `consume_message` pour transférer la propriété du message qui a été réservé.  
  
13. Dans la `protected` section, définissez la `release_message` (méthode).  
  
 [!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_13.h)]  
  
     Un bloc cible appelle `release_message` pour annuler la réservation d’un message.  
  
14. Dans la `protected` section, définissez la `resume_propagation` (méthode).  
  
 [!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_14.h)]  
  
     Le runtime appelle `resume_propagation` après un bloc cible consomme ou libère un message réservé. Cette méthode propage tous les messages qui se trouvent dans la file d’attente de sortie.  
  
15. Dans la `protected` section, définissez la `link_target_notification` (méthode).  
  
 [!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_15.h)]  
  
     Le `_M_pReservedFor` variable de membre est définie par la classe de base `source_block`. Cette variable membre pointe vers le bloc cible, le cas échéant conserve la réservation dans le message qui se trouve au début de la file d’attente de sortie. Le runtime appelle `link_target_notification` lorsqu’une nouvelle cible est liée à la `priority_buffer` objet. Cette méthode propage tous les messages qui se trouvent dans la file d’attente de sortie si aucune cible ne conserve de réservation.  
  
16. Dans la `private` section, définissez la `propagate_priority_order` (méthode).  
  
 [!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_16.h)]  
  
     Cette méthode propage tous les messages de la file d’attente de sortie. Tous les messages dans la file d’attente sont disponible pour chaque bloc cible jusqu'à ce qu’un des blocs cibles accepte le message. La `priority_buffer` classe conserve l’ordre des messages sortants. Par conséquent, le premier message dans la file d’attente de sortie doit être accepté par un bloc cible avant que cette méthode offre un autre message aux blocs cibles.  
  
17. Dans la `protected` section, définissez la `propagate_message` (méthode).  
  
 [!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_17.h)]  
  
     Le `propagate_message` méthode permet la `priority_buffer` classe pour agir en tant que récepteur de message ou la cible. Cette méthode reçoit le message qui est offert par le bloc source fourni et insère ce message dans la file d’attente de priorité. Le `propagate_message` méthode puis envoie de façon asynchrone tous les messages sortants vers les blocs cibles.  
  
     Le runtime appelle cette méthode lorsque vous appelez le [concurrency::asend](../Topic/asend%20Function.md) fonction ou lorsque le bloc de message est connecté à d’autres blocs de message.  
  
18. Dans la `protected` section, définissez la `send_message` (méthode).  
  
 [!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_18.h)]  
  
     Le `send_message` méthode ressemble à `propagate_message`. Toutefois, il envoie les messages de sortie synchrone au lieu de façon asynchrone.  
  
     Le runtime appelle cette méthode pendant une opération d’envoi synchrone, comme lorsque vous appelez le [concurrency::send](../Topic/send%20Function.md) (fonction).  
  
 La `priority_buffer` classe contient des surcharges de constructeur qui sont courantes dans de nombreux types de bloc de message. Un constructeur de surcharges prennent [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) ou [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) objets, qui permettent le bloc de message doivent être gérés par un planificateur de tâches spécifique. D’autres surcharges de constructeur acceptent une fonction de filtre. Les fonctions de filtre permettent aux blocs de messages accepter ou rejeter un message en fonction de sa charge utile. Pour plus d’informations sur les filtres de messages, consultez la page [des blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md). Pour plus d’informations sur les planificateurs de tâches, consultez la page [le Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
 Étant donné que la `priority_buffer` classe trie les messages par priorité et ensuite par l’ordre dans lequel les messages sont reçus, cette classe est particulièrement utile lorsqu’il reçoit des messages de façon asynchrone, par exemple, lorsque vous appelez le [concurrency::asend](../Topic/asend%20Function.md) fonction ou lorsque le bloc de message est connecté à d’autres blocs de message.  
  
 [[Haut](#top)]  
  
##  <a name="a-namecompletea-the-complete-example"></a><a name="complete"></a> L’exemple complet  
 L’exemple suivant montre la définition complète de la `priority_buffer` classe.  
  
 [!code-cpp[concrt-priority-buffer#18](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_19.h)]  
  
 L’exemple suivant exécute simultanément un nombre de `asend` et [concurrency::receive](../Topic/receive%20Function.md) opérations sur un `priority_buffer` objet.  
  
 [!code-cpp[concrt-priority-buffer#19](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-a-custom-message-block_20.cpp)]  
  
 Cet exemple génère la sortie suivante.  
  
```Output  
36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36  
24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24  
12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12  
```  
  
 La `priority_buffer` classe classe les messages par priorité, puis par l’ordre dans lequel elle reçoit des messages. Dans cet exemple, les messages dont la priorité numérique supérieure sont insérés vers l’avant de la file d’attente.  
  
 [[Haut](#top)]  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Copiez l’exemple de code et collez-le dans un projet Visual Studio ou collez la définition de la `priority_buffer` classe dans un fichier nommé `priority_buffer.h` et le programme de test dans un fichier nommé `priority_buffer.cpp` puis exécutez la commande suivante dans une fenêtre d’invite de commandes Visual Studio.  
  
 **CL.exe /EHsc priority_buffer.cpp**  
  
## <a name="see-also"></a>Voir aussi  
 [Procédures pas à pas Runtime d’accès concurrentiel](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Fonctions de passage de message](../../parallel/concrt/message-passing-functions.md)
