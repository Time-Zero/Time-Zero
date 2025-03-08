<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>守静笃 至虚极</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.14/dist/vue.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Microsoft YaHei', sans-serif;
        }

        body {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            min-height: 100vh;
            padding: 2rem;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .title {
            text-align: center;
            margin: 3rem 0;
            position: relative;
            animation: float 2s ease-in-out infinite;
        }

        .title h1 {
            font-size: 2.5rem;
            color: #2c3e50;
            background: linear-gradient(45deg, #4CAF50, #2196F3);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }

        .tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 2rem;
            padding: 2rem;
            background: rgba(255,255,255,0.9);
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .tool-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 1rem;
            transition: all 0.3s ease;
            cursor: pointer;
            border-radius: 10px;
            background: white;
        }

        .tool-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0,0,0,0.15);
        }

        .tool-item img {
            width: 50px;
            height: 50px;
            margin-bottom: 1rem;
            transition: transform 0.3s ease;
        }

        .tool-item:hover img {
            transform: scale(1.2);
        }

        .tool-name {
            font-size: 0.9rem;
            color: #333;
            font-weight: 500;
            text-align: center;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        @media (max-width: 768px) {
            .tools-grid {
                grid-template-columns: repeat(3, 1fr);
                gap: 1rem;
            }
        }
    </style>
</head>
<body>
    <div id="app" class="container">
        <div class="title">
            <h1>守静笃，至虚极</h1>
        </div>

        <h3 style="margin: 2rem 0 1rem; color: #2c3e50;">技术栈与工具:</h3>
        
        <div class="tools-grid">
            <a 
                v-for="tool in tools" 
                :key="tool.name"
                :href="tool.link" 
                target="_blank" 
                rel="noreferrer"
                class="tool-item"
            >
                <img :src="tool.img" :alt="tool.name">
                <span class="tool-name">{{ tool.name }}</span>
            </a>
        </div>
    </div>

    <script>
        new Vue({
            el: '#app',
            data: {
                tools: [
                    { 
                        name: 'Bash', 
                        img: 'https://www.vectorlogo.zone/logos/gnu_bash/gnu_bash-icon.svg',
                        link: 'https://www.gnu.org/software/bash/'
                    },
                    {
                        name: 'C',
                        img: 'https://raw.githubusercontent.com/devicons/devicon/master/icons/c/c-original.svg',
                        link: 'https://www.cprogramming.com/'
                    },
                    {
                        name: 'C++',
                        img: 'https://raw.githubusercontent.com/devicons/devicon/master/icons/cplusplus/cplusplus-original.svg',
                        link: 'https://www.w3schools.com/cpp/'
                    },
                    {
                        name: 'Git',
                        img: 'https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg',
                        link: 'https://git-scm.com/'
                    },
                    {
                        name: 'Linux',
                        img: 'https://raw.githubusercontent.com/devicons/devicon/master/icons/linux/linux-original.svg',
                        link: 'https://www.linux.org/'
                    },
                    {
                        name: 'Python',
                        img: 'https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg',
                        link: 'https://www.python.org'
                    },
                    {
                        name: 'PyTorch',
                        img: 'https://www.vectorlogo.zone/logos/pytorch/pytorch-icon.svg',
                        link: 'https://pytorch.org/'
                    },
                    {
                        name: 'Redis',
                        img: 'https://raw.githubusercontent.com/devicons/devicon/master/icons/redis/redis-original-wordmark.svg',
                        link: 'https://redis.io'
                    },
                    {
                        name: 'TensorFlow',
                        img: 'https://www.vectorlogo.zone/logos/tensorflow/tensorflow-icon.svg',
                        link: 'https://www.tensorflow.org/'
                    }
                ]
            }
        })
    </script>
</body>
</html>
