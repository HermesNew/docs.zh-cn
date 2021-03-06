---
title: ICorDebugVirtualUnwinder 接口
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
ms.openlocfilehash: 532052aa4f869861fbdb40ba0126bfd800eba942
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121875"
---
# <a name="icordebugvirtualunwinder-interface"></a>ICorDebugVirtualUnwinder 接口
提供帮助堆栈展开的方法。  
  
## <a name="methods"></a>方法  
  
|方法|“属性”|  
|------------|----------|  
|[GetContext 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|获取此展开器的当前上下文。|  
|[Next 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|前进到调用方的上下文。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugVirtualUnwinder` 接口的成员由调试器来实现，从而在堆栈展开中提供帮助。  
  
> [!NOTE]
> 此接口仅适用于 .NET Native。 如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
