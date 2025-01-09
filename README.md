 <p align="right"> 
  <img src="https://komarev.com/ghpvc/?username=bearl27" />
 </p>


<h1 align="center">Hi, I'm bearl27  <img src="https://media.giphy.com/media/hvRJCLFzcasrR4ia7z/giphy.gif" width="28"></h1>
<br>

 - 👩‍🎓 I am a student engineer.
 - 🌱 I’m currently learning Unity and webApp!
 - [Twitter - @bearl](https://twitter.com/bearl_develop)
 - [Qiita - @bearl27](https://qiita.com/bearl27)
 - [SpeakerDeck - @bearl](https://speakerdeck.com/bearl27)
 - [Portforio](https://bearl27.github.io/)


<br>

## 🌱 Skills
![My Skills](https://skillicons.dev/icons?i=react)
![My Skills](https://skillicons.dev/icons?i=nextjs)
![My Skills](https://skillicons.dev/icons?i=mui)
![My Skills](https://skillicons.dev/icons?i=tailwind)
![My Skills](https://skillicons.dev/icons?i=html)
![My Skills](https://skillicons.dev/icons?i=css)
![My Skills](https://skillicons.dev/icons?i=js)
![My Skills](https://skillicons.dev/icons?i=ts)
![My Skills](https://skillicons.dev/icons?i=threejs)
![My Skills](https://skillicons.dev/icons?i=blender)
![My Skills](https://skillicons.dev/icons?i=figma)
![My Skills](https://skillicons.dev/icons?i=unity)
![My Skills](https://skillicons.dev/icons?i=cs)
![My Skills](https://skillicons.dev/icons?i=cpp)
![My Skills](https://skillicons.dev/icons?i=python)
![My Skills](https://skillicons.dev/icons?i=androidstudio)
![My Skills](https://skillicons.dev/icons?i=java)
![My Skills](https://skillicons.dev/icons?i=swift)
![My Skills](https://skillicons.dev/icons?i=firebase)
![My Skills](https://skillicons.dev/icons?i=github)



## 🏃‍♀️ Activities
 <p align="left"> 
  <img alt="Top Langs" height="150px" src="https://github-readme-stats.vercel.app/api/top-langs/?username=bearl27&layout=compact&count_private=true&show_icons=true&theme=tokyonight" />
  <img alt="github stats" height="150px" src="https://github-readme-stats.vercel.app/api?username=bearl27&count_private=true&show_icons=true&show_icons=true&theme=tokyonight" />
</p>

[![trophy](https://github-profile-trophy.vercel.app/?username=bearl27&theme=tokyonight&column=7)](https://github.com/bearl27/github-profile-trophy)


[![](https://github-readme-streak-stats.herokuapp.com/?user=bearl27&theme=tokyonight)](https://github-readme-streak-stats.herokuapp.com/?user=bearl27&theme=tokyonight)



```
void KeyEvent(unsigned char key, int x, int y)
{
	if(gamemode == 0){
		if (key == 0x0D) {
			gamemode = 1;
			printf("Game Started\n");
		}
        if (key == 0x1b) {
			Cleanup();
			exit(0);
		}
	}else if(gamemode == 1){
		// ESCキーを入力したらアプリケーション終了
		if (key == 0x1b) {
			Cleanup();
			exit(0);
		}
		// エンターキーで単語チェック
		else if (key == 0x0D && gameStarted) {
			bool correctWordFound = false;

			// 4方向の単語をチェック
			if (!correctWordFound && !wordList.empty()) {
				for (size_t i = 0; i < 4 && i < currentWordList.size(); ++i) {
					if (inputBuffer == currentWordList[i]) {
						printf("正解！%s方向の単語が正解です。次の単語に進みます。\n", directionNames[i]);

						for (int j = 0; j < Object::objects.size(); ++j) {
							if (directionNames[i] == "Top") {
								// 条件に一致するオブジェクトをすべて削除
								Object::objects.erase(
									std::remove_if(Object::objects.begin(), Object::objects.end(),
										[](const Object& obj) {
											return obj.which_circle == 1; // 上方向のオブジェクトを判定
										}),
									Object::objects.end());
							}
							else if (directionNames[i] == "Bottom") {
								// 条件に一致するオブジェクトをすべて削除
								Object::objects.erase(
									std::remove_if(Object::objects.begin(), Object::objects.end(),
										[](const Object& obj) {
											return obj.which_circle == 0; // 下方向のオブジェクトを判定
										}),
									Object::objects.end());
							}
							else if (directionNames[i] == "Left") {
								// 条件に一致するオブジェクトをすべて削除
								Object::objects.erase(
									std::remove_if(Object::objects.begin(), Object::objects.end(),
										[](const Object& obj) {
											return obj.which_circle == 2; // 左方向のオブジェクトを判定
										}),
									Object::objects.end());
							}
							else if (directionNames[i] == "Right") {
								// 条件に一致するオブジェクトをすべて削除
								Object::objects.erase(
									std::remove_if(Object::objects.begin(), Object::objects.end(),
										[](const Object& obj) {
											return obj.which_circle == 3; // 右方向のオブジェクトを判定
										}),
									Object::objects.end());
							}
						}

						correctWordFound = true;

						// 正解時の処理を追加
						showCorrectAnswer = true;
						correctAnswerStartTime = glutGet(GLUT_ELAPSED_TIME);
						correctWord = currentWordList[i];
						correctWordDirection = i;  // 正解の方向を記録
					}
				}
				if (!correctWordFound) {
					printf("不正解。もう一度試してください。\n");
					showFailedAnswer();
				}
			}

			// バッファをクリア
			inputBuffer.clear();
		}
		// バックスペースキー
		else if (key == 0x08 && !inputBuffer.empty()) {
			inputBuffer.pop_back();
		}
		// 通常の文字入力
		else if (key >= 32 && key <= 126) {
			inputBuffer += key;
		}
	}else if(gamemode == 2){
        if (key == 0x0D) {
            gamemode = 0;
            life = 3;
            printf("Press Enter to start the game\n");
        }
        if (key == 0x1b) {
			Cleanup();
			exit(0);
		}
    }
}

```
