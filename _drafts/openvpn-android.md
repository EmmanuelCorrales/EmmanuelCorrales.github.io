---
layout: post
title:  "OpenVPN library for Android"
date:   2016-10-01 00:22:33 +0800
categories: android openvpn vpn
tags: [ android, openvpn, vpn ]
---
<p>For months I've been working on adding OpenVPN features to one of my Android projects. The project is <a href="https://play.google.com/store/apps/details?id=com.surveybods.android">SurveyBods</a> and my client, ResearchBods needed the OpenVPN functionality to perform their "Usage Study" features.
To implement those features, I used
<a href= "https://emmanuelcorrales.github.io/tunnel/">Tunnel</a>
, an OpenVPN library for Android. In this post I'll show you how to use Tunnel to build a simple app that imports an ovpn file then starts a VPN service.</p>

<h3>What is OpenVPN?</h3>
<p>OpenVPN is an open-source software application that implements virtual private network (VPN) techniques for creating secure point-to-point or site-to-site connections in routed or bridged configurations and remote access facilities. It uses a custom security protocol that utilizes SSL/TLS for key exchange.</p>

<h3>How can I use OpenVPN on Android?</h3>
<p>There are many apps in the Google Play Store that can let you to connect with OpenVPN. I suggest you checkout the official OpenVPN app
<a href="https://play.google.com/store/apps/details?id=net.openvpn.openvpn">OpenVPN Connect</a> and Arne Schwabe's
<a href="https://play.google.com/store/apps/details?id=de.blinkt.openvpn">OpenVPN for Android</a>.</p>

<h3>What is Tunnel?</h3>
<p>Tunnel is an open-source Android library project that I started while working for Researchbods. It is based on Arne Schwabe's
<a href="https://play.google.com/store/apps/details?id=de.blinkt.openvpn">OpenVPN for Android</a>.</p>

<h3>TunnelDemo App</h3>
To demonstrate how to use Tunnel, I built a <a href="https://github.com/EmmanuelCorrales/TunnelDemo">TunnelDemo</a> app.

On your project build.gradle file add the repository for
<a href="https://emmanuelcorrales.github.io/tunnel/">Tunnel</a> like below.

{% highlight groovy %}
allprojects {
    repositories {
        jcenter()
        maven {
            url "http://dl.bintray.com/emmanuelcorrales/maven"
        }
    }
}
{% endhighlight %}

Add as dependency on your app module build.gradle file.

{% highlight groovy %}
compile 'com.emmanuelcorrales:tunnel:1.0.0'
{% endhighlight %}