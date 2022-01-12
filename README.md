## helm-study
There are some things that Kubernetes cannot solve or that are outside its scope.
This is one of the reasons why open source projects are so great. They help amazing tools become even more amazing when we combine them with other awesome open-source tools. And often these tools were developed for the sole purpose of filling the gaps. One of these tools is Helm.[collection](https://www.freecodecamp.org/news/what-is-a-helm-chart-tutorial-for-kubernetes-beginners/)

## some details

```
helm create chartname
```

chart.yaml: This is where you'll put the information related to your chart. That includes the chart version, name, and description so you can find it if you publish it on an open repository. Also in this file you'll be able to set external dependencies using the dependencies key.

values.yaml: Like we saw before, this is the file that contains defaults for variables.

templates (dir): This is the place where you'll put all your manifest files. Everything in here will be passed on and created in Kubernetes.

charts: If your chart depends on another chart you own, or if you don't want to rely on Helm's default library (the default registry where Helm pull charts from), you can bring this same structure inside this directory. Chart dependencies are installed from the bottom to the top, which means if chart A depends on chart B, and B depends on C, the installation order will be C ->B ->A.
