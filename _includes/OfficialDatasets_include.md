
## Official datasets <a name="Official_Datasets"></a>

The production group make official datasets which are sets of files which share important characteristics such as experiment, data_tier, data_stream, processing version and processing configuration. Often all you need is an official dataset.

See [DUNE Physics Datasets](https://docs.dunescience.org/cgi-bin/sso/RetrieveFile?docid=29787&filename=DUNEdataset_v1.pdf) for a detailed description. 

### Fast web catalog queries

Go to [dunecatalog](https://dune-tech.rice.edu/dunecatalog/) and log in with your services password. This web application gives DUNE collaborators a single browser-based interface for searching, browsing, and inspecting the experiment's data. From here you can access the files in a given dataset, view file metadata, check Rucio replica information, and trace file provenance — all in the browser.

Choose your apparatus (Far Detector for example), use the category key to further refine your search and then type in keywords.  Here I chose the `Far Detectors` tab and the `FD-VD` category from the pulldown menu. 

![Fast keyword search]({{ site.baseurl }}/fig/keywordquery.png){: .image-with-shadow }

If you click on a dataset you can see a sample of the files inside it. 

![Fast keyword search]({{ site.baseurl }}/fig/datasetsearch.png){: .image-with-shadow }

Scan the file list and click a file name — every file name is a link to that file's own detail page. There you can view the file's Rucio replica info, metadata, and provenance, with one-click copy of the Rucio replica info for use in scripts and other tools.
NOTE: Allow pop-up windows. To retrieve the Rucio replica info you'll need to authenticate once.

![Fast keyword search]({{ site.baseurl }}/fig/rucioreplicainfo.png){: .image-with-shadow }

### You can use the web data catalog to do advanced searches

You can run advanced searches from the Other tab in the web-based Data Catalog. This includes any MQL query with native wildcard syntax, as well as queries to the conditions DB (ProtoDUNE-HD and VD) — where you can search by run, by momentum, or by start/stop date.

![Full query search]({{ site.baseurl }}/fig/otherquery.png){: .image-with-shadow }


You can find a more detailed tutorial for the dunecatalog site at:
[Dune Catalog Tutorial](https://docs.dunescience.org/cgi-bin/sso/RetrieveFile?docid=33738&filename=DUNE_Catalog_User_Guide.pdf&version=3)



### Command line tools and advanced queries 

You can also explore and find the right dataset on the command line by using metacat dataset keys:

First you need to know your namespace and then explore within it.

~~~
metacat namespace list # find likely namespaces
~~~
{: .language-bash}

There are official looking ones like `hd-protodune-det-reco` and ones for users doing production testing like `schellma`.  The default for general use is `usertests`

Creation of namespaces by non-privileged users is currently disabled. A tool is in progress which will automatically make one namespace for each user

### metacat web interface

Metacat also has a web interface that is useful in exploring file parentage [metacat gui](https://metacat.fnal.gov:9443/dune_meta_prod/app/gui)

### Example of finding reconstructed Monte Carlo

Let's look for some reconstructed Monte Carlo from the VD far detector. 

~~~
metacat query "datasets matching fardet-vd:*official having core.data_tier=full-reconstructed"
~~~
{: .language-bash}

Lots of output ... looks like there are 2 types of official ones - let's get "v2"

~~~
metacat query "datasets matching fardet-vd:*v2_official having core.data_tier=full-reconstructed"
~~~
{: .language-bash}

and there are then several different generators. Let's explore reconstructed simulation of the vertical drift far detector. 

~~~
metacat query "datasets matching fardet-vd:*v2_official having core.data_tier=full-reconstructed and dune_mc.gen_fcl_filename=prodgenie_nu_numu2nue_nue2nutau_dunevd10kt_1x8x6_3view_30deg.fcl"
~~~
{: .language-bash}

Ok, found the official neutrino beam dataset:

~~~
fardet-vd:fardet-vd__full-reconstructed__v09_81_00d02__reco2_dunevd10kt_nu_1x8x6_3view_30deg_geov3__prodgenie_nu_numu2nue_nue2nutau_dunevd10kt_1x8x6_3view_30deg__out1__v2_official
~~~
{: .output}

  
~~~
metacat query "datasets matching fardet-vd:*v2_official having core.data_tier=full-reconstructed and dune_mc.gen_fcl_filename=prodgenie_anu_numu2nue_nue2nutau_dunevd10kt_1x8x6_3view_30deg.fcl"
~~~

And the anti-neutrino dataset:

~~~
fardet-vd:fardet-vd__full-reconstructed__v09_81_00d02__reco2_dunevd10kt_anu_1x8x6_3view_30deg_geov3__prodgenie_anu_numu2nue_nue2nutau_dunevd10kt_1x8x6_3view_30deg__out1__v2_official
~~~
{: .output}




