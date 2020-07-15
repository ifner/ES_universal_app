# ES_universal_app

基于嵌入式linux，构建业务无关的应用层框架

计划以下组件：

1、系统层模块：负责linux系统接口的安全调用，二次封装

2、应用核心层模块：负责核心层之上各模块的数据交互，意在解耦各模块间的业务依赖，提供事件驱动、内存管理、缓存队列等

3、通用功能模块：负责提供常用的功能接口调用，如md5、base64、aes\des、json解析、FILE控制接口  等

4、通信层模块：负责常用（通用）的协议通信、流程控制、收发数据缓存（不负责具体业务协议的组包和解析），逐步集合mqtts、http、curl、openssl、json、websocket、rtp等功能（可能会提供设备网页服务功能），考虑是否将具体协议拆分出来。

5、日志管理模块：负责以下功能 分级日志info、本地日志生成、远端日志生成、设备崩溃coredump生成、根据串口命令输出不同等级或模块的日志

6、远程调试模块：负责支持远程调试功能（ssh命令），可以考虑复用通信层相关接口，可以考虑此模块并入日志管理模块

7、交互层模块：提供通用的与客户无关的交互接口，包括设备web端、设备离线接口 等，可以考虑拆分成两个模块，并需要考虑同通信层模块的复用接口

8、GUI模块：不展开

9、通用业务层：根据基线或任务，抽象出通用的业务，在本层进行实现  核心/基础业务功能 ,  ps基线业务协议解析在本层处理，定制协议在定制层处理

10、基线业务层：根据具体任务需求，组合“基础业务层”，提供最终能用的解决方案

11、定制业务层：不展开




Based on embedded Linux, build a business-independent application layer framework

The following components are planned:

1. System layer module: responsible for the safe call of linux system interface, secondary packaging

2. Application core layer module: responsible for the data interaction of the modules above the core layer, intended to decouple the business dependencies between the modules, provide event-driven, memory management, cache queue, etc.

3. General function module: responsible for providing commonly used function interface calls, such as md5, base64, aes\des, json parsing, FILE control interface, etc.

4. Communication layer module: Responsible for common (general) protocol communication, process control, sending and receiving data cache (not responsible for grouping and parsing of specific business protocols), and gradually gather mqtts, http, curl, openssl, json, websocket, rtp, etc. Function (may provide device web service function), consider whether to split the specific agreement.

5. Log management module: responsible for the following functions: hierarchical log info, local log generation, remote log generation, device crash coredump generation, and output of logs of different levels or modules according to serial commands

6. Remote debugging module: responsible for supporting the remote debugging function (ssh command), you can consider multiplexing the relevant interfaces of the communication layer, you can consider this module into the log management module

7. Interaction layer module: Provides a universal and customer-independent interaction interface, including device web end and device offline interface, etc. It can be considered to be split into two modules, and the multiplexing interface with the communication layer module needs to be considered

8. GUI module: do not expand

9. General business layer: Based on the baseline or task, the general business is abstracted, and the core/basic business functions are implemented at this layer. The ps baseline business protocol analysis is processed at this layer, and the custom protocol is processed at the custom layer.

10. Baseline business layer: According to the specific task requirements, the "basic business layer" is combined to provide the final usable solution

11. Customized business layer: do not expand
