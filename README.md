<div align="center">
    <img src="XHS_Downloader_Chrome_Extension_Chrome_ExtensionXHS_Downloader_Chrome_Extension.png" alt="TikTokDownloader" height="256" width="256"><br>
    <h1>小红书作品采集工具</h1>
    <img alt="GitHub" src="https://img.shields.io/github/license/kongzhu2/XHS_Downloader_Chrome_Extension?style=for-the-badge">
    <img alt="GitHub forks" src="https://img.shields.io/github/forks/kongzhu2/XHS_Downloader_Chrome_Extension?style=for-the-badge&color=c56cf0">
    <img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/kongzhu2/XHS_Downloader_Chrome_Extension?style=for-the-badge&color=fff200">
    <img alt="GitHub all releases" src="https://img.shields.io/github/downloads/kongzhu2/XHS_Downloader_Chrome_Extension/total?style=for-the-badge&color=1b9cfc">
    <img alt="GitHub release (with filter)" src="https://img.shields.io/github/v/release/kongzhu2/XHS_Downloader_Chrome_Extension?style=for-the-badge&color=44bd32">
    <hr>
    </div>
    <h1>📝 功能清单</h1>
    <ul>
    <li>采集小红书视频作品信息</li>
    <li>获取小红书视频作品下载地址</li>
    <li>下载小红书视频作品文件</li>
    </ul>
    <h1>📸 程序截图</h1>
    <br>
    <img src="程序截图.png" alt="">
    <h1>🪟 关于终端</h1>
    <p>⭐ 推荐使用 <a href="https://www.microsoft.com/zh-cn/edge/download">Edge浏览器</a> （Windows 11 自带默认终端）运行程序以便获得最佳显示效果！</p>
    <h1>🥣 使用方法</h1>
    <p>如果仅需下载作品文件，选择 <b>直接运行</b> 或者 <b>源码运行</b> 均可，如果需要获取作品信息，则需要进行二次开发进行调用。</p>
    <h2>🖱 直接运行</h2>
    <p>前往 Releases 下载程序压缩包，解压后打开程序文件夹，双击运行 <code>main.exe</code> 即可使用。</p>
    <h2>⌨️ 源码运行</h2>
    <ol>
    <li>安装版本号不低于 <code>3.10</code> 的 Python 解释器</li>
    <li>安装 <code>requirements.txt</code> 包含的第三方模块</li>
    <li>下载本项目最新的源码或 <code>Releases</code> 发布的源码至本地</li>
    <li>运行 <code>main.py</code> 即可使用</li>
    </ol>
    <h2>💻 二次开发</h2>
    <p>如果想要获取小红书图文/视频作品信息，可以根据 <code>main.py</code> 的注释提示进行代码调用。</p>
    <pre>
    # 测试链接
    error_demo = "https://github.com/kongzhu2/XHS_Downloader_Chrome_Extension"
    image_demo = "https://www.xiaohongshu.com/explore/63b275a30000000019020185"
    video_demo = "https://www.xiaohongshu.com/explore/64edb460000000001f03cadc"
    # 实例对象
    path = ""  # 作品下载储存根路径，默认值：当前路径
    folder = "Download"  # 作品下载文件夹名称（自动创建），默认值：Download
    cookie = ""  # 小红书网页版 Cookie
    proxies = None  # 网络代理
    timeout = 5  # 网络请求超时限制，默认值：10
    chunk = 1024 * 1024  # 下载文件时，每次从服务器获取的数据块大小，单位字节
    xhs = XHS(
        path=path,
        folder=folder,
        cookie=cookie,
        proxies=proxies,
        timeout=timeout,
        chunk=chunk, )  # 使用自定义参数
    # xhs = XHS()  # 使用默认参数
    download = True  # 是否下载作品文件
    # 返回作品详细信息，包括下载地址
    print(xhs.extract(error_demo))  # 获取数据失败时返回空字典
    print(xhs.extract(image_demo, download=download))
    print(xhs.extract(video_demo, download=download))
    </pre>
    <h1>⛓ 批量下载</h1>
    <p>在程序所在文件夹创建一个 <code>xhs.txt</code> 文本文件，然后将待处理的作品链接输入文件，每行输入一个作品链接，编辑完成后保存文件，然后运行程序，点击 <code>读取 xhs.txt 文件并批量下载作品</code> 按钮，程序会批量下载每个链接对应的作品文件。</p>
    <h1>⚙️ 配置文件</h1>
    <p>根目录下的 <code>settings.json</code> 文件，可以自定义部分运行参数。</p>
    <table>
    <thead>
    <tr>
    <th align="center">参数</th>
    <th align="center">类型</th>
    <th align="center">含义</th>
    <th align="center">默认值</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td align="center">path</td>
    <td align="center">str</td>
    <td align="center">作品文件储存根路径</td>
    <td align="center">项目根路径</td>
    </tr>
    <tr>
    <td align="center">folder</td>
    <td align="center">str</td>
    <td align="center">作品文件储存文件夹名称</td>
    <td align="center">Download</td>
    </tr>
    <tr>
    <td align="center">cookie</td>
    <td align="center">str</td>
    <td align="center">小红书网页版 Cookie，无需登录；建议自行设置</td>
    <td align="center">内置 Cookie</td>
    </tr>
    <tr>
    <td align="center">proxies</td>
    <td align="center">str</td>
    <td align="center">设置代理</td>
    <td align="center">无</td>
    </tr>
    <tr>
    <td align="center">timeout</td>
    <td align="center">int</td>
    <td align="center">请求数据超时限制，单位：秒</td>
    <td align="center">10</td>
    </tr>
    <tr>
    <td align="center">chunk</td>
    <td align="center">int</td>
    <td align="center">下载文件时，每次从服务器获取的数据块大小，单位：字节</td>
    <td align="center">262144(256KB)</td>
    </tr>
    </tbody>
    </table>
    <h1>🌐 Cookie</h1>
    <ol>
    <li>打开浏览器（可选无痕模式启动），访问小红书任意网页</li>
    <li>按 <code>F12</code> 打开开发人员工具</li>
    <li>选择 <code>控制台</code> 选项卡</li>
    <li>输入 <code>document.cookie</code> 后回车确认</li>
    <li>输出内容即为所需 Cookie</li>
    </ol>
    <br>
    <img src="XHS_Downloader_Chrome_Extension_Chrome_Extension获取Cookie.png" alt="">
    <h1>♥️ 支持项目</h1>
    <p>如果 <b>XHS_Downloader_Chrome_Extension</b> 对您有帮助，请考虑为它点个 <b>Star</b> ⭐，感谢您的支持！</p>
    <h1>⚠️ 免责声明</h1>
    <ul>
    <li>使用者对本项目的使用由使用者自行决定，并自行承担风险。作者对使用者使用本项目所产生的任何损失、责任、或风险概不负责。</li>
    <li>本项目的作者提供的代码和功能是基于现有知识和技术的开发成果。作者尽力确保代码的正确性和安全性，但不保证代码完全没有错误或缺陷。</li>
    <li>使用者在使用本项目时必须严格遵守 <a href="https://github.com/kongzhu2/XHS_Downloader_Chrome_Extension/blob/master/LICENSE">GNU
        General Public License v3.0</a> 的要求，并在适当的地方注明使用了 <a
            href="https://github.com/kongzhu2/XHS_Downloader_Chrome_Extension/blob/master/LICENSE">GNU General Public License
        v3.0</a> 的代码。
    </li>
    <li>使用者在任何情况下均不得将本项目的作者、贡献者或其他相关方与使用者的使用行为联系起来，或要求其对使用者使用本项目所产生的任何损失或损害负责。</li>
    <li>使用者在使用本项目的代码和功能时，必须自行研究相关法律法规，并确保其使用行为合法合规。任何因违反法律法规而导致的法律责任和风险，均由使用者自行承担。</li>
    <li>基于本项目进行的任何二次开发、修改或编译的程序与原创作者无关，原创作者不承担与二次开发行为或其结果相关的任何责任，使用者应自行对因二次开发可能带来的各种情况负全部责任。</li>
    </ul>
    <b>在使用本项目的代码和功能之前，请您认真考虑并接受以上免责声明。如果您对上述声明有任何疑问或不同意，请不要使用本项目的代码和功能。如果您使用了本项目的代码和功能，则视为您已完全理解并接受上述免责声明，并自愿承担使用本项目的一切风险和后果。</b>