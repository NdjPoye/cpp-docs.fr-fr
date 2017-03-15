---
title: "task_options, classe (Runtime d’accès concurrentiel) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppltasks/concurrency::task_options
dev_langs:
- C++
ms.assetid: f93d146b-70f7-46ec-8c2f-c33b8bb0af69
caps.latest.revision: 7
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 9b0d7d245ae204fd59715c8142a836adbb63c10a
ms.lasthandoff: 02/24/2017

---
# <a name="taskoptions-class-concurrency-runtime"></a>task_options, classe (runtime d’accès concurrentiel)
Représente les options autorisées pour la création d’une tâche.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class task_options;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[task_options::task_options, constructeur (Runtime d’accès concurrentiel)](#ctor)|Surchargé. Liste des options de création de tâche par défaut|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[task_options::get_cancellation_token, méthode (Runtime d’accès concurrentiel)](#get_cancellation_token)|Retourne le jeton d'annulation|  
|[task_options::get_continuation_context, méthode (Runtime d’accès concurrentiel)](#get_continuation_context)|Retourne le contexte de continuation|  
|[task_options::get_scheduler, méthode (Runtime d’accès concurrentiel)](#get_scheduler)|Retourne le planificateur|  
|[task_options::has_cancellation_token, méthode (Runtime d’accès concurrentiel)](#has_cancellation_token)|Indique si un jeton d'annulation a été spécifié par l'utilisateur|  
|[task_options::has_scheduler, méthode (Runtime d’accès concurrentiel)](#has_scheduler)|Indique si un planificateur n a été spécifié par l'utilisateur|  
|[task_options::set_cancellation_token, méthode (Runtime d’accès concurrentiel)](#set_cancellation_token)|Définit le jeton donné dans les options|  
|[task_options::set_continuation_context, méthode (Runtime d’accès concurrentiel)](#set_continuation_context)|Définit le contexte de continuation donné dans les options|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `task_options`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** ppltasks.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namegetcancellationtokena--taskoptionsgetcancellationtoken-method-concurrency-runtime"></a><a name="get_cancellation_token"></a>task_options::get_cancellation_token, méthode (Runtime d’accès concurrentiel)  
 Retourne le jeton d'annulation  
  
```
cancellation_token get_cancellation_token() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="a-namegetcontinuationcontexta--taskoptionsgetcontinuationcontext-method-concurrency-runtime"></a><a name="get_continuation_context"></a>task_options::get_continuation_context, méthode (Runtime d’accès concurrentiel)  
 Retourne le contexte de continuation  
  
```
task_continuation_context get_continuation_context() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="a-namegetschedulera--taskoptionsgetscheduler-method-concurrency-runtime"></a><a name="get_scheduler"></a>task_options::get_scheduler, méthode (Runtime d’accès concurrentiel)  
 Retourne le planificateur  
  
```
scheduler_ptr get_scheduler() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="a-namehascancellationtokena--taskoptionshascancellationtoken-method-concurrency-runtime"></a><a name="has_cancellation_token"></a>task_options::has_cancellation_token, méthode (Runtime d’accès concurrentiel)  
 Indique si un jeton d'annulation a été spécifié par l'utilisateur  
  
```
bool has_cancellation_token() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="a-namehasschedulera--taskoptionshasscheduler-method-concurrency-runtime"></a><a name="has_scheduler"></a>task_options::has_scheduler, méthode (Runtime d’accès concurrentiel)  
 Indique si un planificateur n a été spécifié par l'utilisateur  
  
```
bool has_scheduler() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="a-namesetcancellationtokena--taskoptionssetcancellationtoken-method-concurrency-runtime"></a><a name="set_cancellation_token"></a>task_options::set_cancellation_token, méthode (Runtime d’accès concurrentiel)  
 Définit le jeton donné dans les options  
  
```
void set_cancellation_token(cancellation_token _Token);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Token`  
  
##  <a name="a-namesetcontinuationcontexta--taskoptionssetcontinuationcontext-method-concurrency-runtime"></a><a name="set_continuation_context"></a>task_options::set_continuation_context, méthode (Runtime d’accès concurrentiel)  
 Définit le contexte de continuation donné dans les options  
  
```
void set_continuation_context(task_continuation_context _ContinuationContext);
```  
  
### <a name="parameters"></a>Paramètres  
 `_ContinuationContext`  
  
##  <a name="a-namectora--taskoptionstaskoptions-constructor-concurrency-runtime"></a><a name="ctor"></a>task_options::task_options, constructeur (Runtime d’accès concurrentiel)  
 Liste des options de création de tâche par défaut  
  
```
task_options();

task_options(
    cancellation_token _Token);

task_options(
    task_continuation_context _ContinuationContext);

task_options(
    cancellation_token _Token,
    task_continuation_context _ContinuationContext);

template<typename _SchedType>
task_options(
    std::shared_ptr<_SchedType> _Scheduler);

task_options(
    scheduler_interface& _Scheduler);

task_options(
    scheduler_ptr _Scheduler);

task_options(
    const task_options& _TaskOptions);
```  
  
### <a name="parameters"></a>Paramètres  
 `_SchedType`  
 `_Token`  
 `_ContinuationContext`  
 `_Scheduler`  
 `_TaskOptions`  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

