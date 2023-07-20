# On the difficulties in reviewing academic software papers in the earth sciences: a helpful checklist

## Introduction

Creating and maintaining Open and FAIR research software has become an essential part of the scientific endeavor [^1][^2]. Scientists creating software, from simple notebooks to full online platforms, either for themselves and others, are strongly encouraged to share this with fellow scientists through a myriad of publication manners[^3][^4]. However, the main method of sharing, archiving and claiming credit for academic work is here to stay for a while; the classic academic paper[^5]. The structure of the classic paper assumes a typical 'experiment' that is reported upon: 'methods', 'results', 'discussion'. This structure does not work when your contribution to science is not an experiment, but a piece of software such as a new library to standardize (pre)processing steps common in your field[^6], a global circulation model[^7] or a platform to do experiments on[^8]. While as a scientific community we are (slowly) recognizing that such software contributions are an essential part of scientific work, we don't (yet) have a better way to report than writing papers. On the positive side: we have entire journals that focus on publishing peer-reviewed papers on research software like "Environmental Modelling and Software (EMS)", "Journal of Open Source Software (JoSS)" or "Geoscientific Model Development (GMD)".

The function of peer-review in science is to ensure that claims by scientists are checked by fellow scientists before publications. We carefully review each other's methods to make sure the correct conclusion is drawn from the results of the experiment. But what do we check when reviewing a paper describing a new software model? Or a platform for doing science? The reviewers guidelines for GMD still lean on the 'experiment' view of scientific publishing, for example guideline 5: "Are the results sufficient to support the interpretations and conclusions?". But what are the results of a piece of software?

I have recently made a checklist to use when asked to review software contributions to science. I am sharing this checklist here with three goals: 

- it might help others when reviewing (or writing) papers about research software.
- Sharing this checklist also helps in expectation management: by referring to this checklist reviewers can clearly indicate what they did.
- By adopting this checklist as (part of their) reviewers guidelines journals communicate clearly to other scientists, but also to science-journalists and to society at 
large, what it means for a piece of software to be 'peer-reviewed'.

Finally, by sharing this checklist, in the spirit of Open Science, others are given the opportunity to build upon, comment and improve upon the list here provided.

## The checklist

### Introduction:

1. Is the purpose of the paper clearly communicated in the introduction? The most common purpose of a paper on research software is to introduce the software to a broader audience. One other common purpose, often seen by for example papers describing field experiments, is to share lessons learned in the process of building the software with others who are building similar software / projects. Ideally a paper should focus on one message / one purpose. I strongly recommend against mixing introducing new software and introducing new scientific results in the same publication and I encourage journals to not require that new science is part of a software publication.
2. Are other projects or pieces of research software that set out to do similar things properly cited in the introduction? Is it made clear how this software is different from those already existing? "More user friendly" or "more efficient" qualifies as good reasons to make software that otherwise does exactly the same thing as already existing software.

### Describing the software (methods)

3. Are the features of the software clearly explained: what can users do with this piece of software? This is more important (to me as a scientist reviewing the paper) than technical details on how this is achieved (see below).
4. Is it made clear to users how to start using the software? If software needs to be installed, is there (a link to) an installation guide? If the software is (part of) an (online) platform: is it clear how to access the platform?

### Is the software FAIR (Findable, Accessible, Interoperable, Re-usable[^9])

5. Findable: is it clear where the software is available? Best practices include hosting on a package index (PyPi, conda) or on the Research Software Directory[^10]. Is the source code for the software openly available and does it have a persistent identifier such as a DOI through Zenodo? If not, is it clearly explained why not and is this morally acceptable?
6. Interoperable: Is it made clear what (other) software the software depends on? While standard dependencies (os for Python, math for C++) need not be mentioned, depending on 
specialized third party software should clearly be stated.
7. Accessible & re-usable: Is it made clear under what license the software is released, ie. If and how users can build on the software / can use it?

### Sound software practices

8. Does the software comply with the policies on data and software sharing of the journal?
9. Is it made clear what quality control checks were carried out to test if the code contains minimal errors? Reviewing code quality is a task of the team creating the code and should not be assigned to external reviewers: reading other people's code, even if well documented, is hard and many research software projects easily contain thousands of lines of code. Therefore, the authors should communicate how they guarantee code quality. An example of how this could look is provided in the 'contributing' document of the eWaterCycle package[^11]
10. Is the software well documented? Well documented software has both documentation that explains the functions of the software as well as technical documentation on how these functions are achieved and finally documentation for other developers ("How to contribute?"). Functional documentation can for example be a readme file on a github repository for a small project or a complete readthedocs.io page for bigger projects. Technical documentation can be in-line comments for smaller pieces of software or an API reference for online services. Reviewers should sample part of the documentation, but are not expected to read every line of documentation and code.
11. Is it clearly described if and how the software will be maintained after the release of the paper? At the minimum this should include a description of the versioning policy for the code. On the one extreme: "No support / your mileage may vary" is a fair statement, but this needs to be communicated clearly. On the other extreme a community can be in place that maintains the software, including procedures for others on how to contribute. Best practice for describing this (and many more aspects relating to good software practices) is to write a Software Management Plan[^12]

### Demonstrated to work:

12. Is it shown that the software does indeed deliver its claims? This is best showcased through providing convincing use cases of both entry level, typical and expert use of the software. Use cases should focus on the features of the software and ideally not introduce new science / answer new science questions. A good practice is to use the software to show how previous published research is made easier / more accessible / faster by using the new software. This makes sure that the review discussion is not on (the merit of) the science, but focuses on the software, which is the focus of the paper.
13. Can I as a reviewer experience the software firsthand? This can be achieved by explaining how to install it, provide a link to an online environment where the software is running, etc. As a reviewer I will not review every line of the source code (see point 9 above) but I do want to test basic functionality. The best way to facilitate this is to have scripts / notebooks / code that generate the results of the use cases presented (see point 12) available for reviewers to interact with.

## Looking forward

The checklist presented above is intended as a helpful tool for researchers who need to review software-papers and is written with current publication practices in mind. The 'recognition and reward' movement advocates for recognizing the broadness and diversity of the work that scientists do, including writing software. I hope to facilitate that change by providing a way to make the peer review of research software a more transparent process. I recognize that scientific publishing and peer review are evolving. Some of the checks suggested above might not be needed, or would need to be changed, in the future. For example, I hope that in the future points 3, 5, 7 and 8 are routinely checked by the editorial team of a journal before the paper is sent out to reviewing scientists.

## Concluding

Presented are the thirteen checks I do when reviewing an academic paper introducing new research software. This checklist is greatly influenced by the "[Hydrologists Guide to Open Science](https://doi.org/10.5194/hess-26-647-2022)[^13]" and on working with Research Software Engineers from the Netherlands eScienceCenter on the eWaterCycle project[^14]. Many thanks to the co-authors and colleagues who influenced my thinking on this subject.

This checklist is a continuous work in progress: additions are more than welcome to be shared. To facilitate this, I created this Github repository where through pull requests anyone can add their own suggestions to this list.

[^1]: https://doi.org/10.17226/25303

[^2]: https://doi.org/10.1038/d41586-018-02741-4

[^3]: https://doi.org/10.5194/gmd-12-2215-2019

[^4]: https://doi.org/10.25495/7gxk-rd71

[^5]: https://doi.org/10.1029/2018WR024053

[^6]: https://doi.org/10.5281/zenodo.3401363

[^7]: https://doi.org/10.5194/gmd-9-1937-2016

[^8]: https://doi.org/10.5194/gmd-15-5371-2022

[^9]: https://doi.org/10.15497/RDA00068

[^10]: https://research-software-directory.org/

[^11]: [https://doi.org/10.5281/zenodo.5119389](https://doi.org/10.5281/zenodo.5119389)

[^12]: [http://doi.org/10.5281/zenodo.7038280](http://doi.org/10.5281/zenodo.7038280)

[^13]: [https://doi.org/10.5194/hess-26-647-2022](https://doi.org/10.5194/hess-26-647-2022)

[^14]: [https://doi.org/10.5194/gmd-15-5371-2022](https://doi.org/10.5194/gmd-15-5371-2022)
