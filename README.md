# ES_universal_app

基于嵌入式linux，构建业务无关的应用层框架

***
<br><br>
### 计划以下组件：
#### 1、系统层模块：
负责linux系统接口的安全调用，二次封装 
<br>
#### 2、应用核心层模块
负责核心层之上各模块的数据交互，意在解耦各模块间的业务依赖，提供事件驱动、内存管理、缓存队列等
<br/>
#### 3、工具类模块
负责提供常用的工具接口调用，如md5、base64、aes\des、json解析、FILE控制接口  等，ps或可去除此模块，以零散的三方库形式
<br/>
#### 4、通信基础层模块
负责常用（通用）的协议通信、流程控制、收发数据缓存（不负责具体业务协议的组包和解析）ps思考缓存队列是复用 “核心层” 还是内建
<br/>
#### 5、通信协议层模块
网络通信：逐步集合mqtts、http、curl、openssl、json、websocket 等功能（可能会提供设备网页服务功能） ps 视频rtp等或拆为独立模块提供能力
工业通信：提供串口通信相关接口，iic、spi、can等，驱动层提供原始接口，本模块要进行封装 ps思考串口通信的数据缓存队列是内部处理还是用“通信基础层”或“app核心层”
<br/>
#### 5、日志管理模块
负责以下功能 分级日志info、本地日志生成、远端日志生成、设备崩溃coredump生成、根据串口命令输出不同等级或模块的日志
<br/>
#### 6、远程调试模块
负责支持远程调试功能（ssh命令），可以考虑复用通信层相关接口，可以考虑此模块并入日志管理模块
<br/>
#### 7、交互层模块
提供通用的与客户无关的交互接口，包括设备web端、设备离线接口 等，可以考虑拆分成两个模块，并需要考虑同通信层模块的复用接口
<br/>
#### 8、GUI模块
不展开
<br/>
#### 9、通用业务层
根据基线或任务，抽象出通用的业务，在本层进行实现  核心/基础业务功能 ,  ps基线业务协议解析在本层处理，定制协议在定制层处理
<br/>
#### 10、基线业务层
根据具体任务需求，组合 “通用业务层” ，提供最终能用的基线业务方案
<br/>
#### 11、定制业务层
不展开
<br/><br/><br/><br/><br/>



Based on embedded Linux, build a business-independent application layer framework

### Plan the following components:
#### 1. System layer module:
Responsible for safe call of linux system interface, secondary packaging
<br>
#### 2. Application core module
Responsible for the data interaction of the modules above the core layer, intended to decouple the business dependencies between the modules, provide event-driven, memory management, cache queues, etc.
<br/>
#### 3. Tools module
Responsible for providing commonly used tool interface calls, such as md5, base64, aes\des, json parsing, FILE control interface, etc. ps may remove this module in the form of a scattered three-party library
<br/>
#### 4. Communication basic layer module
Responsible for common (universal) protocol communication, process control, and sending and receiving data cache (not responsible for specific business protocol grouping and parsing) PS thinks whether the cache queue reuses the "core layer" or built-in
<br/>
#### 5. Communication protocol layer module
Network communication: gradually integrate functions such as mqtts, http, curl, openssl, json, websocket (may provide device web service functions) ps video rtp, etc. or split into independent modules to provide capabilities
Industrial communication: provide serial communication related interfaces, iic, spi, can, etc., the driver layer provides the original interface, this module needs to be packaged ps thinking whether the serial data communication queue of the serial communication is processed internally or uses the "communication base layer" or "app core layer" "
<br/>
#### 5. Log management module
Responsible for the following functions: hierarchical log info, local log generation, remote log generation, device crash coredump generation, and output of logs of different levels or modules according to serial commands
<br/>
#### 6. Remote debugging module
Responsible for supporting the remote debugging function (ssh command), you can consider multiplexing the relevant interfaces of the communication layer, you can consider this module into the log management module
<br/>
#### 7. Interactive layer module
Provide a universal and customer-independent interaction interface, including device web end and device offline interface. You can consider splitting into two modules, and you need to consider the multiplexing interface with the communication layer module.
<br/>
#### 8, GUI module
Do not expand
<br/>
#### 9, General Business Layer
According to the baseline or task, the general business is abstracted and the core/basic business functions are implemented at this layer. The ps baseline business protocol analysis is processed at this layer, and the custom protocol is processed at the custom layer
<br/>
#### 10. Baseline Business Layer
According to the specific task requirements, combine the "general business layer" to provide a baseline business solution that can be finally used
<br/>
#### 11. Customized business layer
Do not expand
<br/><br/><br/><br/><br/>
