<template>
  <div class="container">
    <div style="height:50px"></div>
    <div class="columns">
      <tooltip label="top-right" placement="top">
        <button class="button is-primary has-text-centered">
          <span>top-right</span>
        </button>
      </tooltip>
      <div>{{ showModal }}</div>
      <button class="button is-primary" @click="showModal = true">Modal</button>
      <modal title="modal弹出" ok-text="确定" :visible.sync="showModal" :on-ok="cb2">
        <p>modal content</p>
      </modal>
      <div class="block is-flex">
        <tabs animation="fade" :only-fade="false">
          <tab-pane label="Pictures">Pictures Tab</tab-pane>
          <tab-pane label="Music" :on-tab-click="cb2">{{ msg }}</tab-pane>
          <tab-pane label="Videos" :on-tab-click="cb1" selected>Video Tab</tab-pane>
          <tab-pane label="Documents" disabled>Document Tab</tab-pane>
        </tabs>
      </div>
      <div class="column is-flex">
        <tabs type="toggle">
          <tab-pane label="Pictures">Pictures Tab</tab-pane>
          <tab-pane label="Music">Music Tab</tab-pane>
          <tab-pane label="Videos">Video Tab</tab-pane>
          <tab-pane label="Documents">Document Tab2</tab-pane>
        </tabs>
      </div>
    </div>
    <div class="columns">
      <div class="column is-2">
        <dropdown text="button下拉" type="button" class="is-primary">
          <div slot="dropdown-content"><p>sadfsdf</p><p>sadfsdf</p><p>sadfsdf</p></div>
        </dropdown>
      </div>
      <div class="column is-2">
        <dropdown text="下拉菜单">
          <ul slot="dropdown-menu">
            <li><a href="javascript:void(0)">link1 link1</a></li>
            <li><a href="">link1 link1</a></li>
            <li><a href="">link1 link1</a></li>
            <li><a href="">link1 link1</a></li>
          </ul>
        </dropdown>
      </div>
      <div class="column is-2">
        <dropdown text="button下拉" type="button" class="is-success">
          <ul slot="dropdown-menu">
            <li><a href="javascript:void(0)">link1 link1</a></li>
            <li><a href="">第一个菜单项</a></li>
            <li><a href="">第二个菜单项</a></li>
            <li><a href="">第三个菜单项</a></li>
          </ul>
        </dropdown>
      </div>
      <div class="column is-3">
        <datepicker :config="{ wrap: true }" placeholder="填写日期" readonly>
          <a class="button" data-toggle><i class="fa fa-calendar"></i></a>
          <a class="button" data-clear><i class="fa fa-close"></i></a>
        </datepicker>
      </div>
      <div class="column">
        <datepicker :config="{ }" placeholder="填写日期" readonly></datepicker>
      </div>
    </div>
    <div class="columns">
      <div class="column is-4">
        <breadcrumb :list="links"></breadcrumb>
      </div>
      <div class="column is-4">
        <breadcrumb>
          <li><a href="">首页</a></li>
          <li><a href="">新闻中心</a></li>
          <li><a href="">国内新闻</a></li>
          <li><a href="">奥运取得第16金</a></li>
        </breadcrumb>
      </div>
      <div class="column">
        <affix>
          <alert :closable="true" title="请注意,倒车!" type="info">
            Lorem ipsum dolor sit amet, consectetur
            adipiscing elit lorem ipsum dolor sit amet,
            consectetur adipiscing elit
          </alert>
        </affix>
      </div>
    </div>
    <div class="columns">
      <div class="column is-2">
        <affix :offset="300"><button class="button">affixed 100px</button></affix>
      </div>
    </div>
    <div class="columns">
      <div class="column is-2"><button class="button" @click="showAside = true">Aside</button></div>
      <div class="column is-2"><button class="button" @click="notify()">Notify</button></div>
      <div class="column is-2"><button class="button" @click="notifyTitle()">Notify With Title</button></div>
      <div class="column">
        <timeline>
          <timeline-item date="Sun, 11 Feb" icon="twitter">asdfasdfasdf</timeline-item>
          <timeline-item >
            <p>adipiscing elit lorem ipsum dolor sit amet, consectetur adipiscing elit</p>
            <p><a href="">news center</a></p>
          </timeline-item>
          <timeline-item date="3 minutes ago" icon="wechat">90980</timeline-item>
        </timeline>
      </div>
    </div>
    <div class="columns">
      <div class="column is-3">
        <menu></menu>
      </div>
      <div class="column is-4">
        <tabs animation="fade" :only-fade="false" type="slideshow">
          <tab-pane label="Pictures">
            <img data-src="holder.js/900x500/auto/#777:#555/text:First slide" alt="First slide [900x500]"
                 src="data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiIHN0YW5kYWxvbmU9InllcyI/PjxzdmcgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB3aWR0aD0iOTAwIiBoZWlnaHQ9IjUwMCIgdmlld0JveD0iMCAwIDkwMCA1MDAiIHByZXNlcnZlQXNwZWN0UmF0aW89Im5vbmUiPjxkZWZzLz48cmVjdCB3aWR0aD0iOTAwIiBoZWlnaHQ9IjUwMCIgZmlsbD0iIzc3NyIvPjxnPjx0ZXh0IHg9IjMxNy43NDIxODc1IiB5PSIyNTAiIHN0eWxlPSJmaWxsOiM1NTU7Zm9udC13ZWlnaHQ6Ym9sZDtmb250LWZhbWlseTpBcmlhbCwgSGVsdmV0aWNhLCBPcGVuIFNhbnMsIHNhbnMtc2VyaWYsIG1vbm9zcGFjZTtmb250LXNpemU6NDJwdDtkb21pbmFudC1iYXNlbGluZTpjZW50cmFsIj5GaXJzdCBzbGlkZTwvdGV4dD48L2c+PC9zdmc+" data-holder-rendered="true">
          </tab-pane>
          <tab-pane label="Music">
            <img data-src="holder.js/900x500/auto/#666:#444/text:Second slide" alt="Second slide [900x500]"
                 src="data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiIHN0YW5kYWxvbmU9InllcyI/PjxzdmcgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB3aWR0aD0iOTAwIiBoZWlnaHQ9IjUwMCIgdmlld0JveD0iMCAwIDkwMCA1MDAiIHByZXNlcnZlQXNwZWN0UmF0aW89Im5vbmUiPjxkZWZzLz48cmVjdCB3aWR0aD0iOTAwIiBoZWlnaHQ9IjUwMCIgZmlsbD0iIzY2NiIvPjxnPjx0ZXh0IHg9IjI3Ny4yODkwNjI1IiB5PSIyNTAiIHN0eWxlPSJmaWxsOiM0NDQ7Zm9udC13ZWlnaHQ6Ym9sZDtmb250LWZhbWlseTpBcmlhbCwgSGVsdmV0aWNhLCBPcGVuIFNhbnMsIHNhbnMtc2VyaWYsIG1vbm9zcGFjZTtmb250LXNpemU6NDJwdDtkb21pbmFudC1iYXNlbGluZTpjZW50cmFsIj5TZWNvbmQgc2xpZGU8L3RleHQ+PC9nPjwvc3ZnPg==" data-holder-rendered="true">
          </tab-pane>
        </tabs>
      </div>
      <div class="column is-2">
        <tag type="primary" size="small" :closable="true">标签</tag>
        <tag type="success" size="">标签1</tag>
      </div>
    </div>
    <div class="columns">
      <div class="column">
        <progress-bar :percent="45" type="danger"></progress-bar>
        <progress-bar :percent="percent" type="danger" :striped="true" :animated="true" :showinfo="true"></progress-bar>
        <button class="button is-info" @click="setPercent(85)">85%</button>
        <button class="button is-info" @click="setPercent(50)">50%</button>
      </div>
    </div>
    <div class="columns">
      <div class="column is-3">
        <collapse accordion>
          <collapse-item title="Component">Lorem ipsum dolor sit amet, consectetur
            adipiscing elit lorem ipsum dolor sit amet,
            consectetur adipiscing elit</collapse-item>
          <collapse-item title="Component2" isactive>Lorem ipsum dolor sit amet, consectetur
            adipiscing elit lorem ipsum dolor sit amet,
            consectetur adipiscing elit</collapse-item>
        </collapse>
      </div>
      <div class="column is-9">
        <steps type="line" :current="0">
          <step :title="title" description="举头望明月">
            <p>1.床前明月光，疑是地上霜。举头望明月，低头思故乡</p>
          </step>
          <step title="Eating" description="春晓">
            <p>2.春眠不觉晓，处处闻啼鸟。夜来风雨声，花落知多少。</p>
          </step>
          <step title="Swimming" description="春夜喜雨">
            <p>3.好雨知时节，当春乃发生。随风潜入夜，润物细无声</p>
          </step>
        </steps>
      </div>
    </div>
    <div style="height: 1920px"></div>
  </div>
  <aside :show.sync="showAside" placement="right" title="aside标题" :width="320"></aside>
  <aside :show.sync="showAside" title="aside标题 left">
    <div class="columns">
      <div class="column is-4">
        <breadcrumb :list="links"></breadcrumb>
      </div>
      <div class="column is-4">
        <breadcrumb>
          <li><a href="">首页</a></li>
          <li><a href="">新闻中心</a></li>
          <li><a href="">国内新闻</a></li>
          <li><a href="">奥运取得第16金</a></li>
        </breadcrumb>
      </div>
    </div>
  </aside>
</template>

<script>
import Tooltip from './spark/Tooltip.vue';
import Modal from './spark/Modal.vue';
import { Tabs, TabPane } from './spark/tab';
import Dropdown from './spark/Dropdown';
import Datepicker from './spark/datepicker/Datepicker.vue';
import Breadcrumb from './spark/Breadcrumb';
import Affix from './spark/Affix';
import Aside from './spark/Aside';
import Notify from './spark/notify';
import { Timeline, TimelineItem } from './spark/timeline';
import Menu from './spark/menu/Menu.vue';
import Tag from './spark/Tag.vue';
import Alert from './spark/Alert.vue';
import ProgressBar from './spark/ProgressBar.vue';
import { Collapse, CollapseItem } from './spark/collapse';
import Steps from './spark/step/Steps.vue';
import Step from './spark/step/Step.vue';

export default {
  data() {
    return {
      msg: 'Hello World!',
      tips: 'show tips',
      showModal: false,
      showAside: false,
      title: 'Shopping',
      percent: 45,
      cb: () => {
        console.log(this.msg);
      },
      links: [
        { name: '首页', path: '/' },
        { name: '全部比赛', path: '/tournament' },
        { name: '创建比赛', path: '/create' },
        { name: '竞速赛,比赛中...' },
      ],
    };
  },
  components: {
    Tooltip,
    Modal,
    Tabs,
    TabPane,
    Dropdown,
    Datepicker,
    Breadcrumb,
    Affix,
    Aside,
    Timeline,
    TimelineItem,
    Menu,
    Tag,
    Alert,
    ProgressBar,
    Collapse,
    CollapseItem,
    Steps,
    Step,
  },
  methods: {
    cb1() {
      console.log('cb1');
    },
    cb2() {
      console.log(this.tips);
    },
    notify() {
      const loading = Notify.loading({ message: '云主机启动中...' });
      setTimeout(() => {
        loading.$destroy(true);
      }, 155500);
    },
    notifyTitle() {
      Notify.success({ title: '成功', message: '删除主机成功!' });
    },
    setPercent(val) {
      this.percent = val;
    },
  },
};
</script>
