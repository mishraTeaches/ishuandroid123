package com.example.newboston;

import android.app.Activity;
import android.content.Intent;
import android.media.MediaPlayer;
import android.os.Bundle;

public class Splash extends Activity {
MediaPlayer ourSong;
	@Override
	protected void onCreate(Bundle ishumishra) {
		// TODO Auto-generated method stub
		super.onCreate(ishumishra);
		setContentView(R.layout.ic_launcherweb);
		 ourSong=MediaPlayer.create(Splash.this, R.raw.songs);
		ourSong.start();
		Thread timer=new Thread(){
		public void run(){
			try{
				sleep(50000);
			}catch(InterruptedException e){
				e.printStackTrace();
			}finally{
				Intent openStartingPoint=new Intent("com.example.newboston.MAINACTIVITY");
			startActivity(openStartingPoint);
			}
		}
	};
	timer.start();
	}

	@Override
	protected void onPause() {
		// TODO Auto-generated method stub
		super.onPause();
		ourSong.release();
		finish();
	}

}

