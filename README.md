# CustomListView
package com.tianyu.customlistview;

import java.util.ArrayList;
import java.util.HashMap;

import android.app.Activity;
import android.os.Bundle;
import android.widget.ListView;

import com.tianyu.customlistview.adapter.ListViewAdapter;

public class MainActivity extends Activity {
	private ListView mListView;
	private ListViewAdapter mListViewAdapter;
	private ArrayList<ArrayList<HashMap<String, Object>>> mArrayList;

	@Override
	protected void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		setContentView(R.layout.activity_main);
		init();
	}

	private void init() {
		mListView = (ListView) findViewById(R.id.listView);
		initData();
		mListViewAdapter = new ListViewAdapter(mArrayList, MainActivity.this);
		mListView.setAdapter(mListViewAdapter);
	}

	private void initData() {
		mArrayList = new ArrayList<ArrayList<HashMap<String, Object>>>();
		HashMap<String, Object> hashMap = null;
		ArrayList<HashMap<String, Object>> arrayListForEveryGridView;

		for (int i = 0; i < 10; i++) {
			arrayListForEveryGridView = new ArrayList<HashMap<String, Object>>();
			for (int j = 0; j < 5; j++) {
				hashMap = new HashMap<String, Object>();
				hashMap.put("content", "i=" + i + " ,j=" + j);
				arrayListForEveryGridView.add(hashMap);
			}
			mArrayList.add(arrayListForEveryGridView);
		}

	}
}
