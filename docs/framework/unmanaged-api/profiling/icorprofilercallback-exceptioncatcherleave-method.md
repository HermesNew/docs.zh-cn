---
title: ICorProfilerCallback::ExceptionCatcherLeave 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherLeave
helpviewer_keywords:
- ExceptionCatcherLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCatcherLeave method [.NET Framework profiling]
ms.assetid: 1f3dbdf5-db0c-4b07-bbb7-375de2a63673
topic_type:
- apiref
ms.openlocfilehash: 7d61a6db8f42398a0d6e0d818605592f4fe71cf7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445010"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a>ICorProfilerCallback::ExceptionCatcherLeave 方法
通知探查器控制正在从相应的 `catch` 块传递出去。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a>备注  
 探查器不应在此方法的实现中被阻止，因为堆栈可能不处于允许垃圾回收的状态，因此无法启用抢先垃圾回收。 如果探查器在此处阻止并且试图进行垃圾回收，则运行时将被阻止，直到此回调返回。  
  
 探查器的此方法的实现不应调入托管代码或以任何方式导致托管内存分配。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ExceptionCatcherEnter 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)
